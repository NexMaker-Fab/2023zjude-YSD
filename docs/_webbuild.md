## <font color="#99CCFF">网站搭建</font>

我们使用GitHub+Docsify完成网站搭建，Docsify是一个简单的文档网站生成器，GitHub提供了一个免费的、团队友好的网站文件管理服务。
***

### 1 工具选择
① 需要创建一个属于自己的GitHub账号

② 下载[Git](https://git-scm.com/)、[GitHub Desktop](https://desktop.github.com/)、[VScode](https://code.visualstudio.com/)和[Picgo](https://picgo.github.io/PicGo-Doc/zh/)

③ 下载[nodejs](https://www.runoob.com/nodejs/nodejs-install-setup.html)来配置环境
***

### 2 建立Web页面
#### ① 创建团队仓库
- 需要由老师创建一个团队仓库

#### ② 网站页面部署
- 在GitHub上部署团队的网页，我们会得到一个空白的网页和一个链接。



### 3 本地设置
#### ① 本地克隆Web页面文件
- 每次修改Web文件内容时，都需要将最新版本的Web文件克隆到本地。GitHub Desktop提供了这个功能，使操作变得非常简单。

#### ② 使用Docsify编辑网页
- 确保在安装Docsify之前安装了nodejs.


- 使用命令行语句在终端安装Docsify

>`npm i docsify-cli -g`

- 确定位置，然后初始化环境

>`docsify init ./docs`

!> 注意  我们遇到的问题


- 运行并预览

>`docsify serve docs`

- 网站链接就会生成：http://localhost:3000

- 设置index.html和sidebar，其代码如下

```HTML
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="UTF-8">
  <title>Document</title>
  <meta http-equiv="X-UA-Compatible" content="IE=edge,chrome=1" />
  <meta name="description" content="Description">
  <meta name="viewport" content="width=device-width, initial-scale=1.0, minimum-scale=1.0">
  <link rel="stylesheet" href="//cdn.jsdelivr.net/npm/docsify@4/lib/themes/vue.css">
</head>
<body>
  <div id="app"></div>
  <script>
    window.$docsify = {
      name: '',
      repo: '',
      loadSidebar: true,
      coverpage: true,
    }
  </script>
  <!-- Docsify v4 -->
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
</body>
</html>
```

- 创建“_sidebar.md”，并输入侧边栏的内容。侧边栏代码如下

```HTML
<div align= 'center'>
  < img src="https://github.com/Fy1307/IMGofSixGod/blob/master/img/logo.jpg?raw=true" width = "200"/>
</div>

* TEAM INTRODUCE
  * [Team Introduction](teamintro.md)
  * [Feng Yujuan ๑ᵒᯅᵒ๑ ](FYJ.md)
  * [Guo Kewei| ᐕ)⁾⁾](GKW.md)
  * [Lu Yue ⌓‿⌓ ](LY.md)
  * [Wang Shuyi oi-io ](WSY.md)
  * [Zhao Kayu !_! ](ZKY.md)
* COURSE PRACTICE
* FINAL PROJECT
```
#### ③ 上传GitHub
- 使用GitHub Desktop上传更改，并在GitHub上查看Web结果。

#### ④ Web图片资源管理
- 为了减少web文件占用的空间，我们使用GitHub+PicGo将文件上传到我们的图像仓库，并直接在Web文件中引用图像地址。

- 创建一个映像存储库，并为PicGo生成一个密钥。

- 该密钥可以通过GitHub生成

- 要在md文档中插入图像,请获取需要在图像存储库中引用的图像地址。

### 参考网站
[过程教学](https://www.nexmaker.com/doc/1projectmanage/github&docsify.html)

[Docsify](https://docsify.js.org/#/)
