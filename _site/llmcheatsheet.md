<style>
/* 现代化的表格样式 */
.llm-table {
    border-collapse: separate;
    border-spacing: 0;
    width: 100%;
    background-color: #fff;
    border-radius: 8px;
    overflow: hidden;
    box-shadow: 0 4px 6px rgba(0, 0, 0, 0.1);
    border: 2px solid #e2e8f0;
    margin: 0;
    position: static;
    transform: none;
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Helvetica, sans-serif;
}

.llm-table th,
.llm-table td {
    padding: 12px 15px;
    text-align: left;
    border-top: 0.5px solid #e2e8f0;
    border-bottom: 1px solid #e2e8f0;
    border-left: 0.5px solid #e2e8f0;
    border-right: 0.5px solid #e2e8f0;
}

.llm-table th {
    background-color: #f8fafc;
    font-weight: 600;
    color: #1a202c;
    position: sticky;
    top: 0;
    z-index: 10;
}

.llm-table tbody tr:hover {
    background-color: #f7fafc;
    transition: background-color 0.2s ease;
}

/* 链接样式 */
.llm-table a {
    color: #3182ce;
    text-decoration: none;
    transition: color 0.2s ease;
}

.llm-table a:hover {
    color: #2c5282;
    text-decoration: underline;
}

/* 表头排序指示器 - 注释掉 */
/* .llm-table th {
    cursor: pointer;
    user-select: none;
}

.llm-table th::after {
    content: '⇅';
    margin-left: 8px;
    opacity: 0.5;
    font-size: 0.8em;
} */

/* 响应式设计 */
@media (max-width: 768px) {
    .table-container {
        resize: vertical; /* 在移动设备上只允许垂直调整 */
    }
}

/* 高亮当前排序列 - 注释掉 */
/* .llm-table th.sort-asc::after {
    content: '↑';
    opacity: 1;
}

.llm-table th.sort-desc::after {
    content: '↓';
    opacity: 1;
} */

.model-params {
    background: #f8f9fa;
    border-radius: 8px;
    padding: 20px 25px;
    margin: 20px 0;
    box-shadow: 0 2px 4px rgba(0,0,0,0.05);
}

.model-params-list {
    list-style: none;
    padding: 0;
    margin: 0;
    display: grid;
    grid-template-columns: repeat(3, 1fr);
    gap: 12px;
}

.model-params-item {
    display: flex;
    align-items: center;
    padding: 8px 12px;
    background: white;
    border-radius: 6px;
    border-left: 4px solid #3182ce;
    transition: transform 0.2s ease;
}

.model-params-item:hover {
    transform: translateX(5px);
}

.model-params-item sub {
    color: #4a5568;
}

.model-params-title {
    font-size: 1.2em;
    color: #2d3748;
    margin-bottom: 15px;
    font-weight: 600;
}

/* 响应式设计 */
@media (max-width: 768px) {
    .model-params-list {
        grid-template-columns: repeat(2, 1fr); /* 平板设备显示两列 */
    }
}

@media (max-width: 480px) {
    .model-params-list {
        grid-template-columns: 1fr; /* 手机设备显示单列 */
    }
}

/* 为合并单元格的第一行添加深色背景 */
.llm-table tbody tr td[rowspan] {
    background-color: #f1f5f9;
    font-weight: 500;
}

/* 确保鼠标悬停效果不会覆盖合并单元格的背景色 */
.llm-table tbody tr:hover td[rowspan] {
    background-color: #e2e8f0;
}

/* 确保斑马纹不会影响到合并单元格的背景色 */
/* .llm-table tbody tr:nth-child(even) td[rowspan] {
    background-color: #f1f5f9;
} */

/* 当鼠标悬停在偶数行时的合并单元格样式 */
/* .llm-table tbody tr:nth-child(even):hover td[rowspan] {
    background-color: #e2e8f0;
} */

/* 模型组第一行的样式 - 移除 font-weight */
.llm-table tbody tr.model-group-row {
    background-color: #f1f5f9;
}

/* 鼠标悬停效果 */
.llm-table tbody tr.model-group-row:hover {
    background-color: #e2e8f0;
}

/* 确保斑马纹不会影响到这些行 */
/* .llm-table tbody tr.model-group-row:nth-child(even) {
    background-color: #f1f5f9;
} */

/* 鼠标悬停在偶数行时的样式 */
.llm-table tbody tr.model-group-row:hover {
    background-color: #e2e8f0;
}

/* 为每个模型组之间添加粗分隔线 */
.llm-table tbody tr:has(+ tr.model-group-row) {
    border-bottom: 2px solid #cbd5e1;
}

/* 兼容性方案：通过 JavaScript 添加类 */
.llm-table tbody tr.model-group-last {
    border-bottom: 2px solid #cbd5e1;
}

/* 添加表格容器样式 */
.table-container {
    overflow: auto;
    resize: both; /* 允许双向调整大小 */
    max-width: 100%;
    min-width: 50%;  /* 防止表格太窄 */
    min-height: 200px; /* 防止表格太矮 */
    border: 1px solid #e2e8f0;
    padding: 10px;
    margin: 20px auto;
    position: relative;
    left: 50%;
    transform: translateX(-50%);
}
</style>

<div class="model-params">
    <div class="model-params-title">列名的含义</div>
    <ul class="model-params-list">
        <li class="model-params-item">M: 模型参数量</li>
        <li class="model-params-item">T: 模型预训练tokens</li>
        <li class="model-params-item">zh: 模型是否很好的支持中文</li>
        <li class="model-params-item">code: 模型是否支持code</li>
        <li class="model-params-item">S: 模型的context sequence长度, 1K=1024</li>
        <li class="model-params-item">L: 模型non-embedding的层数</li>
        <li class="model-params-item">D: 模型token embedding维度</li>
        <li class="model-params-item">F: FFN中隐向量d<sub>ff</sub>维度</li>
        <li class="model-params-item">H: Multi-head attention中head数</li>
        <li class="model-params-item">G: Grouped Query Attention (GQA)中key/value head数</li>
        
        <li class="model-params-item">V: 词表大小</li>
        <li class="model-params-item">Type: 模型类型(Dense/MoE/Mamba/...)</li>
        <li class="model-params-item">Tie: 是否tie embedding</li>
        <!-- <li class="model-params-item">时间: 模型发布时间</li> -->
        
    </ul>
</div>



<table class="llm-table">
  <thead>
    <tr>
      <th>LLM</th>
      <th>M</th>
      <th>T</th>
      <th>zh</th>
      <th>code</th>
      <th>S</th>
      <th>L</th>
      <th>D</th>
      <th>F</th>
      <th>H</th>
      <th>G</th>
      <th>V</th>
      <th>Tie</th>
      <th>Type</th>
      <th>时间</th>
      <!-- <th>公司</th> -->
    </tr>
  </thead>
  <tbody>

    <tr >
      <td >GPT-1</td> 
      <td><a href="https://huggingface.co/openai-community/openai-gpt/blob/main/config.json">117M</a></td>
      <td>800M(w)</td>
      <td>False</td>
      <td>False</td>
      <td>512</td>
      <td>12</td>
      <td>768</td>
      <td>3072</td>
      <td>12</td>
      <td>12</td>
      <td>40478</td>
      <td>True</td>
      <td>Dense</td>
      <td>2018-06-11</td>
    </tr>

    <!-- <GPT-2> -->
    <tr class="model-group-row">
      <td rowspan="4">GPT-2</td> 
      <td><a href="https://huggingface.co/openai-community/gpt2/blob/main/config.json">124M</a></td>
      <td>10B</td>
      <td>False</td>
      <td>False</td>
      <td>1K</td>
      <td>12</td>
      <td>768</td>
      <td>3072</td>
      <td>12</td>
      <td>12</td>
      <td>50257</td>
      <td>True</td>
      <td>Dense</td>
      <td>2019-02-14</td>
    </tr>

    <tr>
      <td><a href="https://huggingface.co/openai-community/gpt2-medium/blob/main/config.json">355M</a></td>
      <td>10B</td>
      <td>False</td>
      <td>False</td>
      <td>1K</td>
      <td>24</td>
      <td>1024</td>
      <td>4096</td>
      <td>16</td>
      <td>16</td>
      <td>50257</td>
      <td>True</td>
      <td>Dense</td>
      <td>2019-02-14</td>
    </tr>
   
    <tr>
      <td><a href="https://huggingface.co/openai-community/gpt2-large/blob/main/config.json">774M</a></td>
      <td>10B</td>
       <td>False</td>
      <td>False</td>
      <td>1K</td>
      <td>36</td>
      <td>1280</td>
      <td>5120</td>
      <td>20</td>
      <td>20</td>
      <td>50257</td>
      <td>True</td>
      <td>Dense</td>
      <td>2019-02-14</td>
    </tr>

    <tr>
      <td><a href="https://huggingface.co/openai-community/gpt2-xl/blob/main/config.json">1.5B</a></td>
      <td>10B</td>
      <td>False</td>
      <td>False</td>
      <td>1K</td>
      <td>48</td>
      <td>1600</td>
      <td>6400</td>
      <td>25</td>
      <td>25</td>
      <td>50257</td>
      <td>True</td>
      <td>Dense</td>
      <td>2019-02-14</td>
    </tr>
    
    <!-- <GPT-3>                                    -->

    <tr class="model-group-row">
      <td rowspan="8">GPT-3</td> 
      <td>125M</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>12</td>
      <td>768</td>
      <td>3072</td>
      <td>12</td>
      <td>12</td>
      <td>50257</td>
      <td>True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>

    <tr>
    <td>350M</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>24</td>
      <td>1024</td>
      <td>4096</td>
      <td>16</td>
      <td>16</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>
    <tr>
    <td>760M</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>24</td>
      <td>1536</td>
      <td>6144</td>
      <td>16</td>
      <td>16</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>
    <tr>
    <td>1.3B</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>24</td>
      <td>2048</td>
      <td>8192</td>
      <td>24</td>
      <td>24</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>
    <tr>
    <td>2.7B</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>32</td>
      <td>2560</td>
      <td>10240</td>
      <td>32</td>
      <td>32</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>
    <tr>
    <td>6.7B</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>32</td>
      <td>4096</td>
      <td>16384</td>
      <td>32</td>
      <td>32</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>
    <tr>
    <td>13B</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>40</td>
      <td>5120</td>
      <td>20480</td>
      <td>40</td>
      <td>40</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>
    <tr>
    <td>175B</td>
      <td>300B</td>
      <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>96</td>
      <td>12288</td>
      <td>49152</td>
      <td>96</td>
      <td>96</td>
      <td>50257</td>
      <td>?True</td>
      <td>Dense</td>
      <td>2020-05-28</td>
    </tr>




    <!-- <Llama 1> -->

    <tr class="model-group-row">
      <td rowspan="4">Llama 1</td> 
      <td><a href="https://huggingface.co/huggyllama/llama-7b/blob/main/config.json">7B</a></td>
      <td>1T</td>
       <td>False</td>
      <td>False</td>
      <td>2K</td>
      <td>32</td>
      <td>4096</td>
      <td>11008</td>
      <td>32</td>
      <td>32</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-02-24</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/huggyllama/llama-13b/blob/main/config.json">13B</a></td>
      <td>1T</td>
      <td>False</td>
      <td>True</td>
      <td>2K</td>
      <td>40</td>
      <td>5120</td>
      <td>13824</td>
      <td>40</td>
      <td>40</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-02-24</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/huggyllama/llama-30b/blob/main/config.json">33B</a></td>
      <td>1.4T</td>
      <td>False</td>
      <td>True</td>
      <td>2K</td>
      <td>60</td>
      <td>6656</td>
      <td>17920</td>
      <td>52</td>
      <td>52</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-02-24</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/huggyllama/llama-65b/blob/main/config.json">65B</a></td>
      <td>1.4T</td>
      <td>False</td>
      <td>True</td>
      <td>2K</td>
      <td>80</td>
      <td>8192</td>
      <td>22016</td> 
      <td>64</td>
      <td>64</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-02-24</td>
      <!-- <td>Meta</td> -->
    </tr>



    <!-- <Llama 2> -->



    <tr>
      <td rowspan="3">Llama 2</td> 
      <td><a href="https://huggingface.co/meta-llama/Llama-2-7b-hf/blob/main/config.json">7B</a></td>
      <td>2T</td>
      <td>False</td>
      <td>True</td>
      <td>4K</td>
      <td>32</td>
      <td>4096</td>
      <td>11008</td>
      <td>32</td>
      <td>32</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-07-18</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/meta-llama/Llama-2-13b-hf/blob/main/config.json">13B</a></td>
      <td>2T</td>
      <td>False</td>
      <td>True</td>
      <td>4K</td>
      <td>40</td>
      <td>5120</td>
      <td>13824</td>
      <td>40</td>
      <td>40</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-07-18</td>
      <!-- <td>Meta</td> -->
    </tr>
   
    <tr>
      <td><a href="https://huggingface.co/meta-llama/Llama-2-70b-hf/blob/main/config.json">70B</a></td>
      <td>2T</td>
      <td>False</td>
      <td>True</td>
      <td>4K</td>
      <td>80</td>
      <td>8192</td>
      <td>28672</td>
      <td>64</td>
      <td>8</td>
      <td>32000</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-07-18</td>
      <!-- <td>Meta</td> -->
    </tr>
    

    <tr>
      <td rowspan="2">Llama 3</td> 
      <td><a href="https://huggingface.co/meta-llama/Meta-Llama-3-8B/blob/main/config.json">8B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>8K</td>
      <td>32</td>
      <td>4096</td>
      <td>14336</td>
      <td>32</td>
      <td>8</td>
      <td>128256</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-04-18</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/meta-llama/Meta-Llama-3-70B/blob/main/config.json">70B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>8K</td>
      <td>80</td>
      <td>8192</td>
      <td>28672</td>
      <td>64</td>
      <td>8</td>
      <td>128256</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-04-18</td>
      <!-- <td>Meta</td> -->
    </tr>

    <tr>
      <td rowspan="3">Llama 3.1</td> 
      <td><a href="https://huggingface.co/meta-llama/Llama-3.1-8B/blob/main/config.json">8B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>128K</td>
      <td>32</td>
      <td>4096</td>
      <td>14336</td>
      <td>32</td>
      <td>8</td>
      <td>128256</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-07-23</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/meta-llama/Llama-3.1-70B/blob/main/config.json">70B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>128K</td>
      <td>80</td>
      <td>8192</td>
      <td>28672</td>
      <td>64</td>
      <td>8</td>
      <td>128256</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-07-23</td>
      <!-- <td>Meta</td> -->
    </tr>

    <tr>
      <td><a href="https://huggingface.co/meta-llama/Llama-3.1-405B/blob/main/config.json">405B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>128K</td>
      <td>126</td>
      <td>16384</td>
      <td>53248</td>
      <td>128</td>
      <td>8</td>
      <td>128256</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-07-23</td>
      <!-- <td>Meta</td> -->
    </tr>


    <tr>
      <td rowspan="2">Llama 3.2</td> 
      <td><a href="https://huggingface.co/meta-llama/Llama-3.2-1B/blob/main/config.json">1B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>128K</td>
      <td>16</td>
      <td>2K</td>
      <td>8192</td>
      <td>32</td>
      <td>8</td>
      <td>128256</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-09-25</td>
      <!-- <td>Meta</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/meta-llama/Llama-3.2-3B/blob/main/config.json">3B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>128K</td>
      <td>28</td>
      <td>3072</td>
      <td>8192</td>
      <td>24</td>
      <td>8</td>
      <td>128256</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-09-25</td>
      <!-- <td>Meta</td> -->
    </tr>

    <tr>
      <td>Llama 3.3 </td>
      <td><a href="https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct/blob/main/config.json">70B</a></td>
      <td>15T</td>
      <td>False</td>
      <td>True</td>
      <td>128K</td>
      <td>80</td>
      <td>8192</td>
      <td>28672</td>
      <td>64</td>
      <td>8</td>
      <td>128256</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-12-06</td>
      <!-- <td>Meta</td> -->
    </tr>



    <!-- qwen -->



    <tr>
      <td rowspan="4">Qwen 1</td> 
      <td><a href="https://huggingface.co/Qwen/Qwen-1_8B/blob/main/config.json">1.8B</a></td>
      <td>2.2T</td>
      <td>True</td>
      <td>True</td>
      <td>8K</td>
      <td>24</td>
      <td>2048</td>
      <td>11008</td>
      
      <td>16</td>
      <td>16</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-11-30</td>
      <!-- <td>Alibaba</td> -->
      <!-- ... 更多列 ... -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen-7B/blob/main/config.json">7B</a></td>
      <td>2.4T</td>
      <td>True</td>
      <td>True</td>
      <td>8K</td>
      <td>32</td>
      <td>4096</td>
      <td>22016</td>
      <td>32</td>
      <td>32</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-11-30</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen-14B/blob/main/config.json">14B</a></td>
      <td>3T</td>
      <td>True</td>
      <td>True</td>
      <td>2K</td>
      <td>40</td>
      <td>5120</td>
      <td>27392</td>
      <td>40</td>
      <td>40</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-11-30</td>
      <!-- <td>Alibaba</td> -->

    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen-72B/blob/main/config.json">72B</a></td> 
      <td>3T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>80</td>
      <td>8192</td>
      <td>49152</td>
      <td>64</td>
      <td>64</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-11-30</td>
      <!-- <td>Alibaba</td> -->
    </tr>

    
    <!-- qwen 1.5 -->
    <tr>
      <td rowspan="9">Qwen1.5</td> 
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-0.5B/blob/main/config.json">0.5B</a></td>
      <td>2.4T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>24</td>
      <td>1024</td>
      <td>2816</td>
      <td>16</td>
      <td>16</td>
      <td>151936</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-1.8B/blob/main/config.json">1.8B</a></td>
      <td>2.4T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>24</td>
      <td>2048</td>
      <td>5504</td>
      
      <td>16</td>
      <td>16</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-4B/blob/main/config.json">4B</a></td>
      <td>2.4T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>40</td>
      <td>2560</td>
      <td>6912</td>
      
      <td>20</td>
      <td>20</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->

    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-7B/blob/main/config.json">7B</a></td> 
      <td>4T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>32</td>
      <td>4096</td>
      <td>11008</td>
      <td>32</td>
      <td>32</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-14B/blob/main/config.json">14B</a></td> 
      <td>4T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>40</td>
      <td>5120</td>
      <td>13696</td>
      <td>40</td>
      <td>40</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-32B/blob/main/config.json">32B</a></td> 
      <td>?T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>64</td>
      <td>5120</td>
      <td>27392</td>
      <td>40</td>
      <td>8</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-72B/blob/main/config.json">72B</a></td> 
      <td>3T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>80</td>
      <td>8192</td>
      <td>24576</td>
      <td>64</td>
      <td>64</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-110B/blob/main/config.json">110B</a></td> 
      <td>?T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>80</td>
      <td>8192</td>
      <td>49152</td>
      
      <td>64</td>
      <td>8</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>

    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen1.5-MoE-A2.7B/blob/main/config.json">MoE-A2.7B</a></td> 
      <td>?T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>24</td>
      <td>2048</td>
      <td>5632</td>
      <td>16</td>
      <td>16</td>
      <td>151936</td>
      <td>False</td>
      <td>MoE</td>
      <td>2024-02-04</td>
      <!-- <td>Alibaba</td> -->
    </tr>

    <!-- qwen 2 -->
    <tr>
      <td rowspan="5">Qwen2</td> 
      <td><a href="https://huggingface.co/Qwen/Qwen2-0.5B/blob/main/config.json">0.5B</a></td>
      <td>12T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>24</td>
      <td>896</td>
      <td>4864</td>
      <td>14</td>
      <td>2</td>
      <td>151646</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-06-07</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2-1.5B/blob/main/config.json">1.5B</a></td>
      <td>7T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>28</td>
      <td>1536</td>
      <td>8960</td>
      <td>12</td>
      <td>2</td>
      <td>151646</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-06-07</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2-7B/blob/main/config.json">7B</a></td>
      <td>7T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>28</td>
      <td>3584</td>
      <td>18944</td>
      <td>28</td>
      <td>4</td>
      <td>151646</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-06-07</td>
      <!-- <td>Alibaba</td> -->

    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2-72B/blob/main/config.json">72B</a></td>
      <td>7T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>80</td>
      <td>8192</td>
      <td>29568</td>
      <td>64</td>
      <td>8</td>
      <td>151646</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-06-07</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2-57B-A14B/blob/main/config.json">57B-A14B</a></td> 
      <td>4.5T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>28</td>
      <td>3584</td>
      <td>2560</td>
      <td>28</td>
      <td>4</td>
      <td>151646</td>
      <td>False</td>
      <td>MoE</td>
      <td>2024-06-07</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    



    <!-- <qwen2.5> -->
    <tr>
      <td rowspan="7">Qwen2.5</td> 
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-0.5B/blob/main/config.json">0.5B</a></td>
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>24</td>
      <td>896</td>
      <td>4864</td>
      <td>14</td>
      <td>2</td>
      <td>151936</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-09-15</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-1.5B/blob/main/config.json">1.5B</a></td>
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>28</td>
      <td>1536</td>
      <td>8960</td>
      <td>12</td>
      <td>2</td>
      <td>151936</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-09-15</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-3B/blob/main/config.json">3B</a></td>
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>32K</td>
      <td>36</td>
      <td>2048</td>
      <td>11008</td>
      <td>16</td>
      <td>2</td>
      <td>151936</td>
      <td>True</td>
      <td>Dense</td>
      <td>2024-09-15</td>
      <!-- <td>Alibaba</td> -->

    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-7B/blob/main/config.json">7B</a></td> 
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>28</td>
      <td>3584</td>
      <td>18944</td>
      <td>28</td>
      <td>4</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-09-15</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-14B/blob/main/config.json">14B</a></td> 
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>48</td>
      <td>5120</td>
      <td>13824</td>
      <td>40</td>
      <td>8</td>
      <td>151936</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-09-15</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-32B/blob/main/config.json">32B</a></td> 
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>64</td>
      <td>5120</td>
      <td>27648</td>
      <td>40</td>
      <td>8</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-09-15</td>
      <!-- <td>Alibaba</td> -->
    </tr>
    <tr>
      <td><a href="https://huggingface.co/Qwen/Qwen2.5-72B/blob/main/config.json">72B</a></td> 
      <td>?18T</td>
      <td>True</td>
      <td>True</td>
      <td>128K</td>
      <td>80</td>
      <td>8192</td>
      <td>29568</td>
      <td>64</td>
      <td>8</td>
      <td>152064</td>
      <td>False</td>
      <td>Dense</td>
      <td>2024-09-15</td>
    </tr>
    

    <tr>
      <td rowspan="2">DeepSeek LLM</td> 
      <td><a href="https://huggingface.co/deepseek-ai/deepseek-llm-7b-base/blob/main/config.json">7B</a></td>
      <td>2T</td>
      <td>True</td>
      <td>True</td>
      <td>4K</td>
      <td>30</td>
      <td>4096</td>
      <td>11008</td>
      <td>32</td>
      <td>32</td>
      <td>102400</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-11-29</td>
    </tr>
    <tr>
      <td><a href="https://huggingface.co/deepseek-ai/deepseek-llm-67b-base/blob/main/config.json">67B</a></td>
      <td>2T</td>
      <td>True</td>
      <td>True</td>
      <td>4K</td>
      <td>95</td>
      <td>8192</td>
      <td>22016</td>
      <td>64</td>
      <td>8</td>
      <td>102400</td>
      <td>False</td>
      <td>Dense</td>
      <td>2023-11-29</td>
    </tr>

    <tr>
      <td >DeepSeekMoE</td> 
      <td><a href="https://huggingface.co/deepseek-ai/deepseek-moe-16b-base/blob/main/config.json">16B</a></td>
      <td>2T</td>
      <td>True</td>
      <td>True</td>
      <td>4K</td>
      <td>28</td>
      <td>2048</td>
      <td>10944</td>
      <td>16</td>
      <td>16</td>
      <td>102400</td>
      <td>False</td>
      <td>MoE</td>
      <td>2024-01-08</td>
    </tr>

    

  </tbody>
</table>

<script>
// 注释掉排序相关的代码
// function sortTable(n) {
//     const table = document.querySelector(".llm-table");
//     const headers = table.querySelectorAll("th");
//     const tbody = table.querySelector("tbody");
//     const rows = Array.from(tbody.querySelectorAll("tr"));
    
//     headers.forEach(header => {
//         if (header !== headers[n]) {
//             header.classList.remove('sort-asc', 'sort-desc');
//         }
//     });
    
//     const isAscending = !headers[n].classList.contains('sort-asc');
//     headers[n].classList.toggle('sort-asc', isAscending);
//     headers[n].classList.toggle('sort-desc', !isAscending);
    
//     rows.sort((rowA, rowB) => {
//         const cellA = rowA.cells[n].textContent.trim();
//         const cellB = rowB.cells[n].textContent.trim();
        
//         if (!isNaN(cellA) && !isNaN(cellB)) {
//             return isAscending ? 
//                 parseFloat(cellA) - parseFloat(cellB) : 
//                 parseFloat(cellB) - parseFloat(cellA);
//         }
        
//         return isAscending ? 
//             cellA.localeCompare(cellB) : 
//             cellB.localeCompare(cellA);
//     });
    
//     rows.forEach(row => tbody.appendChild(row));
// }

// 注释掉表头点击事件监听器
// document.querySelectorAll('.llm-table th').forEach((header, index) => {
//     header.addEventListener('click', () => sortTable(index));
// });

// 保留模型组样式相关的代码
document.addEventListener('DOMContentLoaded', function() {
    const rows = document.querySelectorAll('.llm-table tbody tr');
    rows.forEach(row => {
        if (row.querySelector('td[rowspan]')) {
            row.classList.add('model-group-row');
        }
    });
});
</script>


