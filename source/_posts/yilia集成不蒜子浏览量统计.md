---
title: yilia集成不蒜子浏览量统计
date: 2018-02-13 12:52:50
toc: true
tags: [hexo,yilia]
---

对于静态blog集成不蒜子非常方便[官方](http://busuanzi.ibruce.info/)

### 1.在相应的全局文件(例：footer.ejs)引入js文件
   （如果是yilia主题放在script.ejs中的main.xxx.js之前，避免全部tag查询界面样式错乱）
``` js
    <script async src="//dn-lbstatics.qbox.me/busuanzi/2.3/busuanzi.pure.mini.js"/>
```
<!--more-->

### 2.每篇文章显示相应的访问量。
    在希望显示的地方添加相应的代码
    ``` html
        <!-- pv的方式，单个用户连续点击n篇文章，记录n次访问量 -->
        <span id="busuanzi_container_site_pv">
            本站总访问量<span id="busuanzi_value_site_pv"></span>次
        </span
    
        <!-- uv的方式，单个用户连续点击n篇文章，只记录1次访客数 -->
        <span id="busuanzi_container_site_uv">
          本站访客数<span id="busuanzi_value_site_uv"></span>人次
        </span>
    ```
<br />

    以yilia主题为例：
#### 2.1.全局统计在footer.ejs里加相应代码
    ``` html
        <footer id="footer">
          <div class="outer">
            <div id="footer-info">
              <div class="footer-left">
                &copy; <%= date(new Date(), 'YYYY') %> <%= config.author || config.title %>
              </div>
              <div class="footer-right">
                <%= config.author || config.title %>
              </div>
              <p>Hosted by <a href="https://pages.coding.me" style="font-weight: bold">Coding Pages</a></p>
            </div>
          </div>
          
          <!-- 添加相应的代码 -->
          <div class="count-span">
            <span id="busuanzi_container_site_pv">
              总访问量: <span id="busuanzi_value_site_pv"></span>|
            </span>
              <span id="busuanzi_container_site_uv">
              总访客: <span id="busuanzi_value_site_uv"></span>
            </span>
          </div>
        </footer>
    ```
    
    
#### 2.2.每个页面单独统计，在article.ejs添加一段代码
    ``` js
        // 在文章tag后面添加相应的访问量    
        <%- partial('post/tag') %>
        
        // 判断是不是主页，如果是主页的tag，这里会全部统计到第一个文章上
        <% if (!index) {%>
            <span id="busuanzi_container_page_pv">|阅读量(<span id="busuanzi_value_page_pv"></span>)</span>
        <% } %>
    ```
    
    