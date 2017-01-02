> 上一篇介绍了如何fork团队的仓库到自己的github，并且clone到本地，不过更新文件push的时候却发生了问题，期间用点击Upload files按钮上传更新文件，虽然这次成功上传了，但问题依然没有解决。这里提供我如何解决问题的方法。

##建立分支

1.在github fork来的仓库里点击Branch:master按钮，如下图操作：
  - 首先在对话框内输入dev，当然可以输入其它。
  - 然后就会弹出图中的按钮，点击它；

![Paste_Image.png](http://upload-images.jianshu.io/upload_images/126870-6499e7173be3ace1.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

2.在本地git命令中，你目前看到的应该是master:

![master.png](http://upload-images.jianshu.io/upload_images/126870-6f06dd127be92d5e.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

3.输入 git branch 查看本地分支，如果你没有clone分支下来那么就只能看到master：

![查看分支.png](http://upload-images.jianshu.io/upload_images/126870-eaa6af22a2c94793.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

4.输入 git branch -a 查看所有的分支（包括了远程的分支），未设置前应该只有红线框中的分支：

![查看所有分支.png](http://upload-images.jianshu.io/upload_images/126870-291de7363585301d.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)


5.根据这两个的区别，就可以创建一个本地分支dev，输入git checkout -b dev origin/dev：创建分支，并把远程分支放在该分支内，切换到该分支。


6.再使用 git branch查看两个分支，可以使用ls查看分支内容。

7.git checkout master 或 git checkout dev 可以互相切换分支。

8.输入git remote -v查看有没有upstream。

9.如果没有则输入： git remote add upstream 他人的仓库地址

10.再次输入git remote -v ；

![upstream.png](http://upload-images.jianshu.io/upload_images/126870-f0899540bff9b667.png?imageMogr2/auto-orient/strip%7CimageView2/2/w/1240)

11.git merge upstream/dev 就会将upstream/dev合并到当前分支dev
##尝试提交push
1.有新文件后，输入git status 查看变化；
2.输入git add -A 
3.输入git commit -m"提交的原因注释可以写在这"
4.输入git push 
然后到github仓库dev分支下查看文件是否push成功。