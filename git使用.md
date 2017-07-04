# git使用

@(git)

##### git添加的html文件，需要在webstrom中按下“！+Tab”生成页面

#### https://git-scm.com/downloads GIT下载地址                                      
>git分布式：可以管理代码，合并代码
>svn：集中式 速度慢，不停的备份

>告诉git你是谁（否则无法提交）
#### 查看当前git配置列表
```
git config --list
```
#### 配置你的账号
```
git config --global user.name 账号
git config --global user.email 邮箱
```
#### 删除文件夹
```
rm -rf .git
rm -rf *git(全部删除)
```
#### 管理文件
>初始化git，告诉git哪个文件夹归你管理
>mkdir 创建目录
>touch 创建文件（可以创建以 . 开头的文件）
>vi index.txt(进入文件写东西)
>进去按i编写
>按ESC输入：wq保存退出

#### 增加暂存区
```
git add .(文件)
```
>在工作区中的文件是红色的，添加到暂存区是绿色的

#### 添加到历史区
```
git commit -m'xxx'
```
###提交
>第一次提交不能使用下面的方法
```
git commit -a -m""
```
>产生冲突需要手动解决，删除不需要的内容，提交最终的结果


### 查看状态
```
git status
```
#### 查看提交日志
```
git log
```
###创建步骤和提交到历史区
>mkdir git-repo
  485  cd git-repo/
  486  clear
  487  git init
  488  ls
  489  ls -a
  490  ls -
  491  ls -a
  492  ls -A
  493  clear
  494  ls -a
  495  touch index.txt
  496  ls
  497  touch .a
  498  clear
  499  ls
  500  vi index.txt 
  501  clear
  502  git init
  503  touch index.txt
  504  git status
  505  clear
  506  git add .
  507  git commit -m '这次为了初始化提交'
  508  clear
  509  git log
  510  vi index.txt 
  511  clear
  512  git diff
  513  clear
  514  git diff --cached
  515  git diff master
  516  clear
  517  git status
  518  clear
  519  git add.
  520  git add .
  521  clear
  522  git commit -m'第二次提交'
  523  clear
  524  git log
	  525  history > 1.txt
#### 移除本次的add
```
git reset HEAD 文件名
```
#### 从暂存区中覆盖掉工作区
```
git checkout 文件名
```
#### 回滚（回到过去）
```
git reset --hard 版本ID
```
#### 恢复未来
```
git reflog
```

>476  git config --list
  477  clear
  478  git config --global user.name zhufengzhufeng
  479  sad
  480  git config --global user.email 894918017@qq.com
  481  clear
  482  git init
  483  rm -rf .git
  484  mkdir git-repo
  485  cd git-repo/
  486  clear
  487  git init
  488  ls
  489  ls -a
  490  ls -
  491  ls -a
  492  ls -A
  493  clear
  494  ls -a
  495  touch index.txt
  496  ls
  497  touch .a
  498  clear
  499  ls
  500  vi index.txt 
  501  vi index.txt 
  502  cat index.txt 
  503  vi index.txt 
  504  cat index.txt 
  505  clear
  506  clear
  507  git status
  508  clear
  509  git add index.txt
  510  git status
  511  clear
  512  git commit
  513  git commit -m"rootCommit"
  514  git status
  515  clear
  516  git log
  517  git status
  518  clear
  519  git diff 
  520  vi index.txt 
  521  git diff
  522  clear
  523  git diff  -- cached
  524  git diff master
  525  clear
  526  git add .
  527  git diff master
  528  clear
  529  git diff 
  530  git diff --cached
  531  clear
  532  git commit -m'addWorld'
  533  clear
  534  git log
  535  clear
  536  git log
  537  git log
  538  git log
  539  clea
  540  clear
  541  git log
  542  clear
  543  ls
  544  vi index.txt 
  545  cat index.txt 
  546  git add .
  547  git status
  548  clear
  549  git reset HEAD index.txt
  550  git status
  551  clear
  552  cat index.txt 
  553  git status
  554  clear
  555  git checkout index.txt
  556  cat index.txt 
  557  git status
  558  git checkout index.txt
  559  ckear
  560  clear
  561  git log
  562  git reset --hard  039b522d63831df98ad0f1dc1459c70
  563  clear
  564  cat index.txt 
  565  git status
  566  git log
  567  clear
  568  git reflog
  569  git reset --hard a2d5f05
  570  cat index.txt 
  571  clear
  572  history > 1.txt

### 分支管理
>查看分支
```
git branch
```
>切换分支
```
git checkout 新建的分支名
```
>删除分支（不能在自己分支上删除自己，只能取别的分支在删除当前分支）
```
git branch -d 新建的分支名
```
>创建并切换分支
```
git checkout -b 新建的分支名
```
>合并分支
- 在master 上合并新建的分支
```
git merge 新建的分支名
```
**只有将内容提交到某个分支上，这个内容才会归属那个分支，别的分支就看不到了**
## 分支
>git branch -D dev
  585  git branch
  586  clear
  587  git branch dev
  588  git checkout dev
  589  git log
  590  clear
  591  git checkout master
  592  git branch -D dev
  593  clear
  594  git checkout -b dev
  595  touch index.js
  596  git checkout master
  597  clear
  598  git checkout dev
  599  git add .
  600  git commit 'addjS'
  601  git commit -m'addjS'
  602  git checkout master
  603  git checkout dev
  604  git checkout master
  605  history > 1.txt


## 提交到远程仓库上
>5
-   git init  一个文件只做一次
-   touch .gitignore 写上忽略的内容
-   创建需要提交的文件（空文件不会被提交）
-  添加到暂存区
-  添加到历史区

### 链接远程仓库
``` 
git remote add 别名(origin) 地址
git remote -v 查看关联的仓库
git remote rm 别名  可以删除链接
```

### 推送

```
git push origin master
```


### 发布github 静态页
>1.必须要有一个固定的分支（gh-pages）
>2.需要将内容发送到这个分支上
>3.在setting中可以免费送你一个网址
**代码：**
```
git checkout -b gh-pages
touch index.html
git add .
git commit -m ""
git push origin gh-pages
```

###克隆
>克隆一次，克隆下来默认会赠送一个地址，可以在这个地址上使用git pull不停的更新数据
```
git clone 别人的地址 别名
git pull origin master 即可（冲突 删除冲突文件 提交后在拉取）
```

##fork 把别人的代码变成自己的
>可以把别人的项目，拷贝一份变成自己的，（别人改了代码）