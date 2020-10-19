#                  Git学习笔记

## 创建版本库

#### 创建仓库并添加文件

1. 选择一个合适的地方，创建一个空目录，目录名最好不含中文

   ```
   $ cd D://git-repositories   ;进入想要建立仓库的目录
   $ mkdir learngit            ;创建空目录
   $ cd learngit               
   $ pwd                       ;pwd命令用来显示当前目录
   /d/git-repositories/learngit
   ```

2. 通过**git init**命令把这个目录变成Git可以管理的仓库

   ```
   $ git init
   Initialized empty Git repository in /d/git-repositories/learngit
   ```

3. 添加文件到Git仓库，分两步：

   - 第一步，使用命令**git add**，可以反复多次使用，添加多个文件
   - 第二步，使用命令**git commit**，把文件提交到仓库

     ```
   $ git add file1.txt
   $ git add file2.txt
   $ git add file3.txt
   $ git commit -m "add 3 files." 
     ```

4. 修改文件用第3条的两个命令即可，可以通过**git status**查看结果，并且用**git diff**可以查看修改的内容

   ```
   $ git diff readme.txt
   ```
   
   
#### 版本回退

1. 使用**git log**命令显示从最近到最远的提交日志，也可以加上参数简化输出的信息

   ```
   $ git log --pretty=oneline
   ```

2. 可以使用**git reset**命令回退到某一个版本

   ```
   $ git reset --hard HEAD^   ;回退到上一个版本
   $ git reset --hard commit_id ;回退到版本号commit_id对应的版本
   ```

3.    *git log*可以查看提交历史，以便确定要回退到哪个版本；要重返未来，*git reflog*查看命令历史，以便确定要回到未来的哪个版本。