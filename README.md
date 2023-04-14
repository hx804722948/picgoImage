![](https://pic1.zhimg.com/v2-ca17038880b7f14bb667684dcea683b8_b.jpg)

随着 Obsidian 公开课的分享，我们建立了关于效率工具的公益群。在群里，我们接触到了很多使用 Obsidian 的小伙伴。

其中，很多小伙伴都提到过一个问题：

> Obsidian 应该怎么管理图片附件呀？
> 
> 图片一多，就让资料库看起来非常混乱。

这篇文章，就帮助你，用一种更好的方式来管理图片附件。

这就是**为你的 Obsidian 建立一个图床。**

## 02 图床

那么，问题来了：什么是图床？

你可以简单的把它理解为**一个专门用于上传图片的网盘**。所有存进去的图片，你都能够得到一个链接，通过这个链接，就能够打开你需要的图片。

这便是：**图片即链接。**

所以，有了图床之后，我在 Obsidian 中插入图片，只需要放一个链接：

![](https://pic4.zhimg.com/v2-0ce233a362b07b4edc6d2719bcbb88d7_b.jpg)

不仅仅是在 Obsidian 中，几乎你在网上看到的大部分图片，其实都有专门的图床。

图床所带的好处，主要有两点：

第一，**无需管理图片**。放到图床中的图片，你使用它，都只需要一个链接，把这个链接放到你需要的内容中，图片就能展示出来。

第二，**内容与图片完全分离。**

之前，我使用 Bear 来完成写作，图片也是放 Bear 中。后来，我想把 Bear 中的内容迁出，真是大费周章。而迁移的最大难点，便是图片的迁移。

但是，有了图床，这就简单多了：因为我文章中所使用的图片，全都只是链接。

这样一来，我所有的笔记，也就全都只是纯文本。

所以，在未来我可以轻松把所有笔记迁移到一款新的工具中。比如，在 Obsidian 中的笔记，我可以直接全选复制，粘贴到 Typora 中：

![](https://pic1.zhimg.com/v2-97c15786e1f1d5e931edc2c29f8d0a88_b.jpg)

在保持原有的内容和格式不变的条件下，图片也完全不受影响。

## 03 建立自己的图床

了解图床的好处之后，我们就来建立一个自己的图床吧！

整个过程，分为三阶段：

1.  建立存储桶，实现手动上传图片。
2.  配置 Picgo 软件，实现自动上传图片。
3.  设置 Obsidian，实现在 Obsidian 中自动上传图片。

### 1\. 建立存储桶

在本文中，我们建立图床的工具，是**腾讯云对象存储**（COS，以下简称 COS）。

这是一项**收费服务**，但如果你仅把它作为 Obsidian 的图床使用，一年存下 500M 图片，那么年费不会超过 10 元——人人都能承受！

你可以直接在腾讯云的这官网注册账号：[https://cloud.tencent.com](https://link.zhihu.com/?target=https%3A//cloud.tencent.xn--com-t33es65add84u1sidk5hkia6803i)

然后，找到对象存储：

![](https://pic4.zhimg.com/v2-e8b9d957a947610b7485662527b640d3_b.jpg)

并新建一个存储桶，这便是你图床存储图片的地方。

新建存储桶时，你需要输入存储桶名称（不能重名），并选择访问权限为 “公有读私有写” 或“公有读写”，其它无需更改。

![](https://pic4.zhimg.com/v2-6df2f7e101c3d85e0e85050b67ac3797_b.jpg)

之后，你便有了一个自己的存储桶。你可以在 “文件列表” 页面中，自由上传自己的资料了。

![](https://pic2.zhimg.com/v2-10002a856d67dc868832c95351c62b39_b.jpg)

对了，腾讯云 COS 现在是按日计费，所以，**创建之后，记得充一点费用。** 不用充太多，10 块能用很久。

### 2\. 安装并配置 Picgo

现在，存储桶已经有了，你可以在文件列表中，手动上传你的图片了。

但是，如何自动上传呢？

这需要用到一款图床上传工具，名为**Picgo**。

这是一款**免费开源**的软件，但官方下载链接放在 Github，如果无法访问，可以到我们的网盘中下载。

安装好 Picgo 之后，我们需要先为它配置好图床信息。

在 “图床设置” 中，选择“腾讯云 COS”，进行配置：

![](https://pic4.zhimg.com/v2-d1f637bff12186b48b9279cb840d5a53_b.jpg)

需要配置的信息，分为三类：

第一，COS 版本，选择 V5。

第二，SecretID 和 Key，以及 AppID，需要在 “密钥管理” 页面中新建并获取到。页面链接已经放到我们网盘的文档中。

第三，存储空间名和存储区域，可以在 “存储桶列表” 页面中获取到。页面链接也已经放到我们网盘的文档中。

最后，在 Picgo 中，你可以设定 “存储路径”，来指定将图片上传到某个具体的文件夹。设置时，请务必记得在末尾加上斜杠 / 。

设置好之后，打开上传主界面，并将图床选择为 “腾讯云 COS”：

![](https://pic1.zhimg.com/v2-4ba0ff9cdcc32db6d2a05135e57d5284_b.jpg)

在这里，你可以选择一张图片，或者直接将图片拖入到上传区域，便会自动完成上传。

上传完成之后，Picgo 会自动复制指定格式的链接。

### 3\. 在 Obsidian 中自动上传图片

现在，我们已经可以通过 Picgo 实现自动上传图片。

但是，如何在 Obsidian 中实现自动上传呢？

你需要一款名为 “**Image auto upload plugin**” 的 Obsidian 插件，插件的安装包，已经放到我们的网盘中。

安装后，直接使用默认设置，无需做任何更改。

![](https://pic3.zhimg.com/v2-d2dd71ffb60b8aa01ead25e8c7b44176_b.jpg)

之后，你可以将图片粘贴，或拖动到 Obsidian 中，插件和 Picgo 会自动上传图片，并在对应的位置自动插入图片链接予以展示。

请记得：**一定要先打开 Picgo，才能实现自动上传。** 你也可以像我一样，直接把 Picgo 设置为开机启动。

以上，配置完成！

## 04 上传现有图片

从现在开始，你所有 Obsidian 中的图片，都会自动上传到图片，在 Obsidian 中，仅仅保存一个链接。

那么问题来了：我之前笔记中的图片怎么上传呢？

你可以以文章为单位，在 Obsidian 中，按下命令行快捷键 Ctrl / Command + P，并选择 "upload all images"。

![](https://pic3.zhimg.com/v2-2f35982c7e897b44824ea900ad3514ea_b.jpg)

即可将当前笔记中所有的图片上传至图床，并替换相关的链接，非常方便。
