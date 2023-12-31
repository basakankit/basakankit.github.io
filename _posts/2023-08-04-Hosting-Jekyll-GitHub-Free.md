---

layout: post
title:  "Hosting Static Jekyll Blog on GitHub for Free"
date:   2023-08-04 
tags: [Jekyll, GitHub, Git, Markdown, Blog, Website, Windows]
---

Thinking about creating your own blog or website but don’t want to use JavaScript, WordPress or blogger. You want something else. There you got Jekyll, it will help you create yourself static website in a day and you don’t need any prerequisites for that. Even better Jekyll has free hosting with GitHub pages.
You are now really getting interested and want to know more about it, don’t worry I have attached the link of [Jekyll][Jekyll-Docs] and [GitHub pages][GitHub-pages] .

You went through the above links and want to create a static website, and I will guide you through it.


So, lets begin 

### Step 1 – Create yourself a repository in GitHub

Head over to [GitHub][Git-Hub] and click on new green button. There in the create repository button be carefull to write exactly your username otherwise it won't work.



![Creating Repository]({{ "\assets\image.png" }})


Congratulation you have now created your websites repository in GitHub.

### Step 2 - Installing jekyll on your computer and running your website locally

I have shown you on Windows. For other operating systems steps may be a bit different.
We now need to go to [rubyinstaller][ruby-installer] and install ruby with devkit which suits your computer best (it's going to be in bold). Double click on rubyinstaller where it is downloaded. Keep clicking on the next button and then at the end finish button. Now a new window will be opened where it will be written ruby installer for windows. Press on 1, 2 and 3 step by step.Then follow the instructions in the [jekyll website][jekyll-website] .


![Downloading jekyll ]({{ "\assets\Downloading-jekyll.png" }})


Now open the command promt to make sure everything got installed correctly for that give the following commands.


![Cheking in command prompt ]({{ "\assets\Cheking-ruby-gem-jekyll.png" }})


Now a stucture of your website is created. Which you can keep modifying.


Note: To create your own post go to _post file in your local reository and keep your blog in vscode in markdown there. You can refer to my [github repository][github-repository] of this webite.

### Step 3 - Hosting you website on github pages.

You need to install git locally, from [here][-here]. 

Now give the following commands in the command prompt in your local directory where jekyll files and folder are kept:
Note: remove () these while typing on command prompt.

{% highlight ruby %}
1.  git init
2.  git add .
3.  git commit -m "(Any comment you want to give)"  
4.  git remote add origin (link of your github repository)
5.  git push    
{% endhighlight ruby %}

Great, you have pushed all your files in GitHub. Go over to GitHub and you will find all your files which you have pushed.
Now you can search your repository on internet and see your website running.

To know more about Jekyll read my [next blog][next-blog].

[Jekyll-Docs]: https://jekyllrb.com/
[GitHub-pages]: https://pages.github.com/
[Git-Hub]: https://github.com/
[ruby-installer]: https://rubyinstaller.org/downloads/
[jekyll-website]: https://jekyllrb.com/docs/
[github-repository]: https://github.com/basakankit/basakankit.github.io/tree/master
[-here]: https://git-scm.com/downloads
[next-blog]: https://basakankit.github.io/2023/08/05/Tips-for-Improving-Jekyll-Blog.html



