最近在用obsidian写文章的时候，发现一个致命的问题，就是上传的图片是保存在本地的，导致以下几个常见问题：

1.  如果在obsidian写好文章去网站发布的话，图片不能直接简单的复制过去。
2.  因为图片是保存在本地的，导入、导出以前迁移不方便  
    经过研究，发现如果把图片存在图床上，可以完美解决这些问题。  
    原理：  
    所谓图床，通俗点可以理解为用来保存图片的网盘，配置好了图床后，当你再插入图片时，图片会被上传并保存在图床当中，并返回一个图片的链接，这样以后如果文档被移动时就不用考虑图片链接的路径问题了，因为此时的链接指向的是云端而不是本地。  
    实操：  
    结合 [https://blog.csdn.net/qq\_44770178/article/details/128251145](https://link.zhihu.com/?target=https%3A//blog.csdn.net/qq_44770178/article/details/128251145) 设置

**一、注册SM.MS**

[SM.MS](https://link.zhihu.com/?target=https%3A//u.sb/sm-ms/) 是一个免费和收费的图片储存及分享服务（Image Hosting、图床），注册成功即可获得5GB的免费容量。

1.  注册后登录之后点击User——>Dashboard。

![](https://pic1.zhimg.com/v2-f025aad94e0cc6aad885ae45a6dcf488_b.jpg)

image.png

1.  在控制面版，可以看到容量的使用情况，点击API Token，进入API Access界面

![](https://pic1.zhimg.com/v2-017fb0eb9e554b4ef76449cd2b764e28_b.jpg)

Pasted image 20230331093541.png

1.  获取API 以备后用

![](https://pic3.zhimg.com/v2-c6b45cb01875fc4148066fb75b6b0b2e_b.jpg)

Pasted image 20230331093633.png

## **二、安装!**

下载链接：[https://molunerfinn.com/PicGo/](https://link.zhihu.com/?target=https%3A//molunerfinn.com/PicGo/)

安装后，打开PicGo，在图床设置的SM.MS设置中填入刚才生成的密钥，点击确定  

![](https://pic4.zhimg.com/v2-0c7ec29d099c9152ee7339199f6002df_b.jpg)

image.png

![](https://pic3.zhimg.com/v2-a21a152b11de26d7672c9d9d1059d726_b.jpg)

image.png

注意：根据SM.MS官网的提示：`Due to network issues, users from China Mainland are unable to access SM.MS, we have added an alternate domain name smms.app`，这里我们需要在备用上传域名中填上`smms.app`

然后在PicGo设置中设置Server，点击确定即可。

![](https://pic4.zhimg.com/v2-10b0537c1edaf2b3596f39150222810b_b.jpg)

![](https://pic2.zhimg.com/v2-f61c4fad51bc096ef7d584a47646420d_b.jpg)

其他设置推荐：建议开启时间戳重命名，不然存在同名文件会出错

## **三、安装Image auto upload Plugin插件（Obsidian）**

在第三方插件中，安装Image auto upload Plugin

![](https://pic3.zhimg.com/v2-28a7e58ba4a7c264732f6a66f40fadf6_b.jpg)

将PicGo server改为`http://127.0.0.1:36677/upload`即可  

![](https://pic4.zhimg.com/v2-bcbd315c641eecc1524b50f58923850f_b.jpg)

Pasted image 20230331094622.png

## **测试**

此时，Obsidian中插入图片的，链接变成了https开头的，说明图片被上传到了图床当中，这样就不用担心图片丢失的问题了。  

![](https://pic2.zhimg.com/v2-1c7574aff39c59683e2ab001a3224619_b.jpg)

Pasted image 20230331094733.png

并且在SM.MS的Dashboard可以看到图片的源文件
