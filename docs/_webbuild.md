## <font color="#99CCFF">Web Page Construction Process</font>

We used GitHub+Docsify to build the site. Docsify is a simple document site generator. GitHub provides a free, team-friendly website file management page service.

***

### 1 Tool Selection and Configuration Environment
- First， Creating your own [GitHub](https://github.com/) account.

- Download [Git](https://git-scm.com/)、[GitHub Desktop](https://desktop.github.com/)、[VScode](https://code.visualstudio.com/)and [Picgo](https://picgo.github.io/PicGo-Doc/zh/).

- Download [nodejs](https://www.runoob.com/nodejs/nodejs-install-setup.html) to configure your environment.

***

### 2 Create a Web Page
#### ① Create a team repository
- Set up a warehouse that belongs to the team, this step is completed by the teacher.

#### ② Website page deployment
- Deploy the team's web page on GitHub, where we get a blank web page and a link to it.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/%E9%82%80%E8%AF%B7.png?raw=true" width = "1000"/>
</div>

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/add%20people.png?raw=true" width = "1000"/>
</div>

***

### 3 Local Settings
#### ① Clone the Web page file locally
- Each time you modify the content of a Web file, clone the latest version of the Web file to the local PC. GitHub Desktop provides this functionality, making the operation very simple.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/20231006200406.png?raw=true" width = "1000"/>
</div>

#### ② Edit web pages with Docsify
- Make sure you install nodejs before installing Docsify.

- Install Docsify on the terminal using command line statements.

>`npm i docsify-cli -g`

- Determine the location, and then initialize the environment.

>`docsify init ./docs`

!>**Note!!!** the problem we encountered (If you are a Mac user, please skip this step)

An error occurred during initialization. Procedure.

<div align= 'center'>
  <img src="https://raw.githubusercontent.com/bobwu0214/imageuploadservice/main/img/202210122216237.png" width = "500"/>
</div>

Get all the execution policies that affect the current session and display them in priority order:
>`Get-ExecutionPolicy -List

To set an execution policy within a specific range, do the following:
>`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser

Then you can initialize it successfully.

- Run and preview.

>`docsify serve docs`

- The website link will be generated.

- Set index.html和sidebar，The code for index.html is as follows:

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

- Create “_sidebar.md”，and enter the contents of the sidebar. The sidebar code is as follows:

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
#### ③ Upload to GitHub
- Upload changes using GitHub Desktop and view Web results on GitHub.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/%E4%B8%8A%E4%BC%A0%E7%BD%91%E9%A1%B5.png?raw=true" width = "1000"/>
</div>

#### ④ Web image resource management
- In order to reduce the space occupied by Web files, we use GitHub+PicGo to upload files to our gallery repository and reference the image address directly in the Web file.
  
- Create an image repository and generate a key for PicGo.

- The key can be generated via GitHub.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/20231006205307.png?raw=true" width = "1000"/>
</div>

- To insert an image in an md. document, get the image address that you want to reference in the image repository.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/%E5%A4%8D%E5%88%B6%E9%93%BE%E6%8E%A5.png?raw=true" width = "1000"/>
</div>

***

### Reference
[过程教学](https://www.nexmaker.com/doc/1projectmanage/github&docsify.html)

[Docsify](https://docsify.js.org/#/)

[about_Execution_Policies](https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.3)
