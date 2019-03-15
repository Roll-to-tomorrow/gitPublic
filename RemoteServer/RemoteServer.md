## 配置远程服务器
***
使用场景：有本地和远程两台电脑，想要在本地写代码并在远程主机上运行代码。
就需要将在本地写好的代码传输到远程电脑，然后通过本地电脑操作远程电脑，运行远程电脑上的解释器。  
目前总结配置远程服务器共有以下两种方式：
- 桌面操作
- IDE(Pycharm)操作

IDE操作相对于桌面操作的优势在于可以随时修改代码，可以在IDE中直接查看运行结果，操作相对简单，但无法看到服务器主机的
资源使用和配置等情况。
****
### 桌面操作
通过Xmanager管理远程服务器的解释器和ftp  
- step 1. 下载安装[Xmanager](https://pan.baidu.com/s/1b0GCFRkQjn8fP_ShdK5jhg),提取码：lptm     

安装后如下图

![fig1](https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig1.png)   
 
- step 2. 填写需要的参数   
  首先打开Xftp，选择修建会话：
  - 主机填写服务器IP地址
  - 协议选择FTP
  - 端口号填写老师给的FTP端口号 
  - 填写用户名和密码  
  
<img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig2.png' width='380' height='220'/>

- step 3. 上传数据、代码到FTP  
- step 4. 打开Xshell，并新建会话
  - 协议选择SSH
  - 填写主机IP地址
  - 端口号填写老师给的SSH对应的端口
  - 选择用户身份验证填写用户名和密码  
  
<img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig3.jpg' width='380' height='220'/>

- step 5. 用命令行操作远程服务器
  - 比如要运行python代码，首先进入代码所在文件夹，然后以python命令行运行python文件
  > python 文件名.py
***
### Pycharm连接远程服务器
通过pycharm配置python远程解释器
- step 1. 打开pycharm --> Tools --> Development -->Configuration 
 
<img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig4.png' width='380' height='220'/>

- step 2. 配置参数
   - 首先新建一个Server，name随便填，Type选择SFTP
   
   <img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig5.png' width='380' height='220'/>

   - 配置Connection
       - 1号框填写远程服务器IP地址
       - 2号框填写SSH端口号
       - 3号框自动匹配远程服务器操作文件夹，也可以自己填，建议Autodetect
       - 4、5号框填写用户名和密码
       
       <img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig6.png' width='380' height='220'/>

   - 配置Mappings
     - 1号框表示本地文件夹，就是本地保存代码的文件夹
     - 2号框表示远程服务器的操作文件夹
     
     <img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig7.png' width='380' height='220'/>

- step 3. 配置完成后便开始操作本地代码在远程服务器运行
    - 调用远程解释器 File --> Setting --> Project: --> Project Interpreter
    - 点击右上角的齿轮按钮，选择Add Remote
    - 在Configure Remote Pyter Interpreter框中选择Development configuration
    - 下面框中选择刚才配置好的服务器配置，点击确定
    
    <img src='https://github.com/Roll-to-tomorrow/gitDemos/raw/master/RemoteServer/fig8.png' width='380' height='220'/>

- step 4. 本地查看远程服务器中的文件
    - Tools --> Development --> Browse Remote Host
    - 右侧出现的就是你在远程服务器中的文件夹，显示的范围是你在Deployment中的Connection选项卡下配置的Root path路径下的文件及文件夹。

- step 5. 将本地文件上传到远程服务器
    - 右击需要上传的文件或文件名，选择
    > Upload to 服务器名
- step 6. 在IDE中运行代码就可以了