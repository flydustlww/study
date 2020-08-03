<!--
 * @Author: your name
 * @Date: 2020-08-03 13:15:05
 * @LastEditTime: 2020-08-03 13:33:29
 * @LastEditors: Please set LastEditors
 * @Description: In User Settings Edit
 * @FilePath: /study/前沿文章/使用coop coep为浏览器创建更安全的环境.md
--> 
不受同源限制的标签：font video image iframe script它们能加载来自不同源的资源来增强网页功能 但是加大了信息泄露的风险.
一些概念：
1 context Group
context group是一组共享相同上下文的tab window 或者iframe。
例如：如果网站 https://a.example 打开弹出窗口 https://b.example 则打开窗口和弹出窗口共享相同的浏览器上下文，并且它们可以通过dom api相互访问。例如window.opener
2 spectre 漏洞
在cpu中被发现的漏洞，攻击者可读取在统一浏览器下任意context group下的资源
特别时在使用一些需要和计算机硬件交互的api时（sharedArrayBuffer performance.measureMemory js self-profiling api）
3 跨域隔离
为了能够使用这些强大的功能，并且保证我们的网站资源更加安全，我们需要为浏览器创建一个跨域隔离的环境。
coep： cross origin embedder policy 跨源潜入程序策略
coop: cross origin opener policy 跨源开放者策略
我们可以通过coep coop来创建隔离环境

cross-Origin-Embedder-Policy： require corp
cross-Origin-Opener_Policy: same-origin



