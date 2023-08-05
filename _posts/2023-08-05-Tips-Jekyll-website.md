---

layout: post
title:  "Tips for your Jekyll Blog"
date:   2023-08-05

---

You have created yourself a basic jekyll website/blog. But you want to add images and want to properly arrange the files and folder. I will help you out.  The folder where you store all your jekyll files locally give it the same name as your GitHub repository for your blog, for keeping it simple. When you want to write drafts of your new posts try not to write in your repository locally as it can be publicy seen in your GitHub repository. Write outside of the local repository in another folder, you may call it 'drafts'.


![Arranging Folders]({{ "\assets\Arranging_folders.png" }})


Well you have created yourself a nice nice blog, but you want to add images. For that enter your local repository where files and folder like '_posts', '_site' or '_config.yml' are kept. Create a folder called 'assets' here you will store all your images which you are going to use in your blog.


![Arranging Jekyll Files]({{ "\assets\arranged_jekyll_files.png" }})


For attaching that image copy the path of the image and paste it in between the {{}} just like I have attached a screenshot below 


![Image code]({{ "\assets\Screenshot_image.png" }})


One last tip would be to keep your 'local repository' and your 'drafts' folder in cloud locally like in OneDrive, Google Drive or Dropbox. If some how your computer crashes or gets corrupted all your folder and files will be safe. 