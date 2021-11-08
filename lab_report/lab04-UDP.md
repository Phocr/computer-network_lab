#### 实验四

##### Wireshark Lab: UDP

---

阅读对UDP的介绍，然后按照任务中的指导进行操作。打开Wireshark，在其中捕捉一些UDP数据包，筛选出来，并查看详细信息。<img src="lab04-1.png" style="zoom:30%;" />

回答问题：

1. <img src="lab04-2.png" style="zoom:30%;" />

一共4个字段，为Source Port(源端口号)，Destination Port(目的端口号)，Length(长度)，Checksum(校验和)

2. 同1，是8byte

3. Length的长度是UDP报文的字节数

4. 可以根据Length计算得出，Length字段2byte，所以UDP负载为$2^{16}-8=65528$个字节

5. 类似的，端口号从0开始，所以最大端口号应为$2^{16}-1=65535$

6. <img src="lab04-3.png" style="zoom:30%;" />

   由图知协议号十进制为17，十六进制就是0x11

7. 两者的源端口号和目的端口号是互换的

   <img src="lab04-4.png" style="zoom:30%;" />

   <img src="lab04-5.png" style="zoom:30%;" />
