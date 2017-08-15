1. **案例一**：关于width属性值fit-content。   
   **场景描述**：一个table表格，被赋予了bootstrap的table类，所以宽度为100%，各列（td）的宽度有css类进行定义，table外层的div宽度大于该table的各列之和。   
   **实现目标**：让table表格在chrome和IE下都保持宽度等于各列之和。   
   分析和解答：此场景下，表格将会撑开到div的内宽。现在chrome浏览器下，要对该table的宽度进行修正，可以使用width: fit-content;来实现。
   但fit-content值为实验性质的值，在IE10+下也并不支持。于是在IE下的方法则是可以将其宽度设为1px来解决。但目标是要同时支持两个浏览器，首先想到的是css中
   的媒体查询@supports，然而这一特性IE10+也不支持，已知的方案属于hack方法，思路是用IE10+支持的媒体查询的另一个关键字@media来查询IE浏览器才有的属性来
   确定当前浏览器是否是IE，css可以像如下这样来写：
   ```
   .table-width { width: -moz-fit-content; width: -webkit-fit-content; width: fit-content; }
   @media screen and (-ms-high-contrast: active), (-ms-high-contrast: none) { .table-width { width: 1px; } }
   ```
   
