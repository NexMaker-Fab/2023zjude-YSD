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
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E9%82%80%E8%AF%B7.png" width = "1000"/>
</div>

<br>

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/admin.PNG" width = "1000"/>
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

- Open Visual Studio Code, create a new terminal, and enter the following code in the terminal.
<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E7%BB%88%E7%AB%AF.PNG" width = "1000"/>
</div>

>`npm i docsify-cli -g`

- Determine the location, and then initialize the environment.
<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%88%9D%E5%A7%8B%E5%8C%96.PNG" width = "1000"/>
</div>

>`docsify init ./docs`

!> **Note!!!**  

!> The problem we encountered (If you are a Mac user, please skip this step)

An error occurred during initialization. Procedure.

<div align= 'center'>
  <img src="https://raw.githubusercontent.com/bobwu0214/imageuploadservice/main/img/202210122216237.png" width = "500"/>
</div>

Get all the execution policies that affect the current session and display them in priority order:

>`Get-ExecutionPolicy -List`

To set an execution policy within a specific range, do the following:

>`Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`

Then you can initialize it successfully.

- Run and preview.

>`docsify serve docs`

- The website link will be generated.

- Set index.html, sidebar and coverpage，The code for index.html is as follows:

```HTML
<!--index.html-->

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
      loadSidebar: true, //to create a sidebar
      coverpage: true, //to create a coverpage
    }
  </script>
  <!-- Docsify v4 -->
  <script src="//cdn.jsdelivr.net/npm/docsify@4"></script>
</body>
</html>
```

- Create "_sidebar.md", and enter the contents of the sidebar. The sidebar code is as follows:

```HTML
<!--_sidebar.md-->

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
- Create "_coverpage.md", and enter the contents of the coverpage. The coverpage contains a logo image and a button to go to the homepage. The coverpage code is as follows:

```HTML
<!--_coverpage.md-->

<div>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/1ogo.png?raw=true" width = "500"/>
</div> 

# Welcome to Team YSD! 
[Let's go!!!!!](teamintro.md)
```

#### ③ Upload to GitHub
- Upload changes using GitHub Desktop and view Web results on GitHub.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/%E4%B8%8A%E4%BC%A0%E7%BD%91%E9%A1%B5.png?raw=true" width = "1000"/>
</div>

#### ④ Web image resource management
- In order to reduce the space occupied by Web files, we use GitHub+PicGo to upload files to our gallery repository and reference the image address directly in the Web file.
  
- Create an image repository and generate a key for PicGo.
- Go to the GitHub homepage, and click on the profile picture in the top right corner.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E8%BF%9B%E5%85%A5GitHub%E4%B8%BB%E9%A1%B5.PNG" width = "1000"/>
</div>

- Click on "Settings."

 <div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E7%82%B9%E5%87%BB%E8%AE%BE%E7%BD%AE.PNG" width = "1000"/>
</div> 

- Click on "Developer settings"

 <div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/develop%20setting.PNG" width = "1000"/>
</div> 

- Generate a key and choose the classic type.

 <div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E7%94%9F%E6%88%90%E4%B8%AA%E4%BA%BA%E5%AF%86%E9%92%A5.PNG" width = "1000"/>
</div> 

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E7%94%9F%E6%88%90%E5%AF%86%E9%92%A52.PNG" width = "1000"/>
</div> 

- Choose a name and select "no expiration," and make sure to check the "repo" option.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%8B%BE%E7%94%BBrepo.PNG" width = "1000"/>
</div> 

- Click "Generate" to obtain the key.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E5%A4%8D%E5%88%B6%E5%AF%86%E9%92%A5.PNG" width = "1000"/>
</div> 

- Run Picgo and configure the GitHub image hosting settings.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E6%89%93%E5%BC%80GitHub%E5%9B%BE%E5%BA%8A%E8%AE%BE%E7%BD%AE.PNG" width = "1000"/>
</div> 

- Paste the token and customize the domain name. Here's a sample domain name format:https://cdn.jsdelivr.net/gh/username/Repositoryname.@main
- You only need to replace the username and repository name with your own.

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E7%B2%98%E8%B4%B4%E5%9F%9F%E5%90%8D%EF%BC%8C%E5%B9%B6%E8%AE%BE%E7%BD%AE%E8%87%AA%E5%AE%9A%E4%B9%89%E5%9F%9F%E5%90%8D.PNG" width = "1000"/>
</div> 

- To insert an image in an md. document, get the image address that you want to reference in the image repository.

<div align= 'center'>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/%E5%A4%8D%E5%88%B6%E9%93%BE%E6%8E%A5.png?raw=true" width = "1000"/>
</div>

***

### 3 Write the documents with markdown
#### ① Header
```HTML
{
  # First-Level Title
  ## Second-Level Title
  ### Third-Level Title
}
```

- The effect is as follows：
# First-Level Title
## Second-Level Title
### Third-Level Title
  
#### ② Title
- The `#` can be used to indicate 1-6 levels of headings, with `#` for a first level heading, `##` for a second level heading, and so on.
- The sample code is as follows:

```HTML
# This is a first-level title.
## This is a second-level title.
### This is a third-level title.
#### This is a four-level title.
##### This is a five-level title.
###### This is a six-level title.
```
- The effect is as follows：
# This is a first-level title.
## This is a second-level title.
### This is a third-level title.
#### This is a four-level title.
##### This is a five-level title.
###### This is a six-level title.


#### ③ Add an image
- Fill in the name of the image you want to display in `[ ]` and the address of the image in `( )`.
- The sample code is as follows:

```HTML
![logo of fusion360](https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/fusion360_logo.png)
```
- The effect is as follows：
  
![logo of fusion360](https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/fusion360_logo.png)
  
#### ④ Add a link
- Fill in the name of the link you want to display in `[ ]` and the link address in `( )`.
- The sample code is as follows:

```HTML
[Google Scholar](https://scholar.google.com/)
```
- The effect is as follows：<br>
[Google Scholar](https://scholar.google.com/)
  
#### ⑤ Italicize
- In Markdown, you can use an asterisk * or an underscore _ to italicize text. Just add one asterisk or underscore before and after the text you want to italicize.
- The sample code is as follows:
```HTML
Using asterisks: *This text will be italicized*
```
***

### 4 fold and file
- We currently have the following sidebar code.However, there is an issue with the sidebar that prevents it from folding.

```HTML
<div>
  <img src="https://github.com/erkoww/YSD_img/blob/main/img/1ogo.png?raw=true" width="200"/>
</div>

* TEAM INTRODUCE
  * [Team Introduction](teamintro.md)
  * [Feng Yujuan ๑ᵒᯅᵒ๑ ](FYJ.md)
  * [Guo Kewei| ᐕ)⁾⁾](GKW.md)
  * [Lu Yue ⌓‿⌓ ](LY.md)
  * [Wang Shuyi oi-io ](WSY.md)
  * [Zhao Kayu !_! ](ZKY.md)
* COURSE PRACTICE
  * Project Management
    * [Web Page Construction](_webbuild.md)
  * CAD
    * [Fusion 360](_fusion360.md)
  * Arduino
    * [Arduino Basic](_arduino_basic.md)
    * [Arduino Input & Output](_arduino_input_output.md)
    * [Case Study](_cases.md)
  * CNC
    * [CNC manufacture](_cnc.md)
  * 3D Printing
    * [Bambu](_Bambu.md)
  * Computer controlled cutting
    * [Laser cutting](_Computer_controlled_cutting.md)
  * Interface Application Programming
    * [Processing](_processing.md)
  * IoT and Interaction
    * [IoT](_IOT.md)
* FINAL PROJECT
  * [Initial Concept](_concept.md)
```

<div align= 'center'>
  <img src="https://cdn.jsdelivr.net/gh/erkoww/YSD_img/img/%E4%BE%A7%E8%BE%B9%E6%A0%8F%E6%8A%98%E5%8F%A0%E9%97%AE%E9%A2%98.PNG" width = "1000"/>
</div>

- Unfortunately, despite numerous attempts at modification, we still can't fold the sidebar.

### Reference
[过程教学](https://www.nexmaker.com/doc/1projectmanage/github&docsify.html)

[Docsify](https://docsify.js.org/#/)

[about_Execution_Policies](https://learn.microsoft.com/zh-cn/powershell/module/microsoft.powershell.core/about/about_execution_policies?view=powershell-7.3)
