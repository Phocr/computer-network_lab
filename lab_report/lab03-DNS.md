#### 实验三

##### Wireshark Lab: DNS

---



阅读实验文档并进行操作。

1. **nslookup**

   阅读文档，熟悉nslookup的各个操作，并以此完成1，2，3题

   1. 用nslookup访问科大的web，IP地址为202.38.64.246

      <img src="/photos/lab03-1.png" />

	2. 用nslookup确定一个欧洲大学的权威服务器![](/photos/lab03-2.png)
	
	3. 利用2的一个DNS服务器查询Yahoo邮箱的邮件服务器，尝试了一下上面的DNS都不行，似乎是被墙了，但是尝试使用科大的DNS成功查询
	
	   ![](/photos/lab03-3-1.png)
	
	   ![](/photos/lab03-3-2.png)



2. **ipconfig**

   阅读实验文档，熟悉ipconfig

   ![](/photos/lab03-t2.png)

3. **Tracing DNS with Wireshark**

   按照操作清除缓存，打开Wireshark进行捕获，捕获后的结果有点多，干扰较大，回答问题。

   4. ![](D:\Study\大三上\计网\lab\photos\lab03-4.png)

      根据捕获内容，是使用UDP发送

   5. ![](D:\Study\大三上\计网\lab\photos\lab03-5-1.png)
   
      ![](D:\Study\大三上\计网\lab\photos\lab03-5-2.png)
   
      都是53端口
   
   6. 查询消息发送到202.38.64.56
   
      ![](D:\Study\大三上\计网\lab\photos\lab03-6.png)
   
      正是本地DNS服务器地址
   
   7. type是A，Answer RRs：0，查询消息不包含任何answer
   
   8. ![](D:\Study\大三上\计网\lab\photos\lab03-8.png)
   
      回复3条，回复是类型，主机别名，以及两个ip地址
   
   9. ![](D:\Study\大三上\计网\lab\photos\lab03-9.png)
   
      是对应的
   
   10. 并没有，本地的DNS已经缓存了，不需要再查询了
   
   
   
   使用nslookup，查询www.mit.edu，回答问题
   
   11. ![](D:\Study\大三上\计网\lab\photos\lab03-11-1.png)
   
       ![](D:\Study\大三上\计网\lab\photos\lab03-11-2.png)
   
       都是53端口
   
   12. ![](D:\Study\大三上\计网\lab\photos\lab03-12.png)
   
       IP地址202.38.64.56，是本地DNS地址
   
   13. type为A，查询信息没有任何answer
   
   14. ![](D:\Study\大三上\计网\lab\photos\lab03-14.png)
   
       3个回复，包含两个主机别名和一个IP地址
   
   15. ![](D:\Study\大三上\计网\lab\photos\lab03-15.png)
   
       
   
   更换指令重复实验，回答问题
   
   16. IP地址202.38.64.56，是本地服务器DNS地址
   
   17. type是NS，Answer RRs：0，没有任何answer
   
   18. 域名服务器![](D:\Study\大三上\计网\lab\photos\lab03-18.png)
   
       没有提供IP地址
   
   19. ![](D:\Study\大三上\计网\lab\photos\lab03-19.png)
   
   更改指令后重复操作，回答问题
   
   20. 地址是18.0.72.3，不是本地默认DNS服务器地址，这是mit的bitsy.mit.edu的IP地址
   
   21. type是A，Answer RRs：0，没有回复
   
   22. DNS查询失败，从23的截图中看出wireshark中并没有回复，所以answer应该是0
   
       ![](D:\Study\大三上\计网\lab\photos\lab03-22.png)
   
   23. ![](D:\Study\大三上\计网\lab\photos\lab03-23.png)

