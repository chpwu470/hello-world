***

> ## 测试环境部署架构图：

![](https://github.com/chpwu470/hello-world/blob/master/img/testEnvironment.png?raw=true)
***

> ## 测试环境服务器配置：
![](https://github.com/chpwu470/hello-world/blob/master/img/config.png?raw=true)
***

  ## 测试场景1：
**测试目的：**<br>
  评估单volume，单客户端情况下的最高读性能<br>
**测试步骤：**<br>
  单个客户端mount单个volume的情况下，在10*1000个文件夹下准备共1000w个1K大小的文件，使用java FileInputStream方式并发读取文件并判断大小及内容准确性。<br>
**测试结果：**<br>
  ![](https://github.com/chpwu470/hello-world/blob/master/img/testresult1.png?raw=true)<br>
**测试结论：**<br>
  单volume，单客户端的情况下，最高读能力为12000+笔/秒。

  ## 测试场景2：
  **测试目的：**<br>
  评估单volume的最高读性能<br>
  **测试步骤：**<br>
  准备多个客户端（准备了6个，避免瓶颈出现在客户端）来mount同一个volume，在10*1000个文件夹下准备共1000w个1K大小的文件，使用java FileInputStream方式并发读取文件并判断大小及内容准确性。<br>
  **测试结果：**<br>
  ![](https://github.com/chpwu470/hello-world/blob/master/img/testresult2.png?r=true)<br>
**测试结论：**<br>
  单volume，多客户端（6个）的情况下，最高读能力为42000+笔/秒。


