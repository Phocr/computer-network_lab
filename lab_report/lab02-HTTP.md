#### 实验二

##### Wireshark Lab：HTTP

---

阅读实验文档，按照文档进行各个部分的操作。

1. **The Basic HTTP GET/response interaction**

   按照指示操作，打开wireshark，输入http筛选，等待一会开始捕捉，打开网页http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file1.html，停止捕捉，在wireshark中找到对应部分，如图

   <img src="photos\lab02-1.png" style="zoom:50%;" />

   根据捕捉到的结果回答问题：

   1. browser version: 1.1	sever version: 1.1

   2. 在GET中的Hypertext Transfer Protocol下的Accept-Language找到

      Accept-Language: zh-CN,zh;q=0.9,en;q=0.8,en-GB;q=0.7,en-US;q=0.6\r\n

   3. 我的电脑地址：222.195.84.32    server地址：128.119.245.12

      在Internet Protocol中找到

   4. Status code在回复的Hypertext Transfer Protocol中找到

      HTTP/1.1  200  OK\r\n

   5. Last-Modified: Wed, 15 Sep 2021 05:59:01 GMT\r\n

   6. 在回复的Hypertext Transfer Protocol的Content-Length中：

      Content-Length: 128\r\n   

      ​	[Content length: 128]

   7. 有，例如：server

      

2. **The HTTP CONDITIONAL GET/response interaction** 

   按照操作清楚缓存后重新进入网站http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file2.html，在刷新一次，在wireshark中成功抓包：<img src="photos\lab02-3.png" style="zoom:50%;" />

   回答问题：

   8. 并没有发现

   9. 有，在Line-based text data：text/html（10 lines）中<img src="photos\lab02-3-1.png" style="zoom:50%;" />

   10. 有，显示If-Modified-Since: Wed, 15 Sep 2021 05:59:01 GMT\r\n

   11. 回复HTTP/1.1 304 Not Modified\r\n，因为这个页面的缓存还在，文件并没有改变，所以就没有回复内容，直接使用缓存就行

       

3. **Retrieving Long Documents**

   类似2中的操作，清除缓存，进入网站http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file3.html并捕获。

   回答问题

   12. 只有一个GET request，含有GET message for the Bill or Rights的：<img src="photos\lab02-3-2.png" style="zoom:50%;" />

   13. 包含相应的包：<img src="photos\lab02-3-3.png" style="zoom:50%;" />

   14. status code and phrase：200 OK

   15. 需要4个<img src="photos\lab02-3-4.png" style="zoom:50%;" />

       

4. **HTML Documents with Embedded Objects**

   和上面操作类似，清除缓存，进入网站http://gaia.cs.umass.edu/wireshark-labs/HTTP-wireshark-file4.html，捕获。

   回答问题：

   16. <img src="photos\lab02-4.png" style="zoom:50%;" />

       发送了三个HTTP GET请求，地址是128.119.245.12  128.119.145.12  178.79.137.164

   17. 根据捕捉到的结果，应该是串行下载，当pearson.png请求并收到后，发送了BE_cover_small.jpg的请求<img src="photos\lab02-4-1.png" style="zoom:50%;" />
   
       

5. **HTTP Authentication**

   类似的，清楚缓存，进入网站http://gaia.cs.umass.edu/wireshark-labs/protected_pages/HTTP-wireshark-file5.html，输入信息，成功抓包。

   <img src="photos\lab02-5.png" style="zoom:50%;" />

   回答问题：

   18. response：HTTP/1.1 401 Unauthorized  (text/html)

   19. 多了Authorization部分

       <img src="photos\lab02-5-1.png" style="zoom:50%;" />

