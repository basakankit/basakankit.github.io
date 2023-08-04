---

layout: post
title:  "Jekyll in Windows"
date:   2023-08-04  

---

Thinking about creating your own portfolio but don’t want to use JavaScript, WordPress or blogger. You want something else. There you got Jekyll, it will help you create yourself static website in a day and you don’t need any prerequisites for that. Even better Jekyll has free hosting with GitHub pages.
You are now really getting interested and want to know more about it, don’t worry I have attached the link of [Jekyll] [https://jekyllrb.com/] and [GitHub pages] [https://pages.github.com/] .

You went through the above links and want to create a static website, and I will guide you through it.
So, lets begin 

### Step 1 – Create yourself a repository in GitHub

Head over to [https://github.com/] and click on new green button. There in the create repository button be carefull to write exactly your username otherwise it won't work.

<img src="C:\Users\basak\OneDrive\myblog\image.png" alt="alt text" title="New Repository" />

<img src="C:\Users\basak\OneDrive\myblog\Creating_Repository.png" alt="Creating Repository" title="Creating Repository" />

Congratulation you have now created your websites repository in GitHub.

### Step 2 - Installing jekyll on your computer and running your website locally

We now need to go to [https://rubyinstaller.org/downloads/] and install ruby with devkit which suits your computer best (it's going to be in bold). Double click on rubyinstaller where it is downloaded. Keep clicking on the next button and then at the end finish. Now a new window will be opened where it will be written ruby installer for windows. Press on 1, 2 and 3 step by step.
Now open the command promt to make sure everything got installed correctly for that give the following commands.

<img src="C:\Users\basak\OneDrive\myblog\Draft_images\Cheking-ruby-gem-jekyll.png" alt="alt text" title="Creating Repository" />

Then follow the instructions in the jekyll website https://jekyllrb.com/docs/ .

Now a stucture of your website is created. Which you can keep modifying.
Note: To create your own post go to _post file in your local reository and keep your blog in vscode in markdown there.

### Step 3 - Hosting you website on github pages.

You need to install git locally, from https://git-scm.com/downloads. 

Now give the following commands in the command prompt in your local directory where jekyll files and folder are kept:
Note: remove < > these while typing on command prompt.

1.  git init
2.  git add .
3.  git commit -m "<Any comment you want to give>"    remove < > these while typing on command prompt.
4.  git remote add origin <link of your github repository>
5.  git push    

Great, you have pushed all your files in GitHub. Go over to GitHub and you will find all your files which you have pushed.



