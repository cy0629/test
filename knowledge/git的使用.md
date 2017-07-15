## git的命令
### 1.help  
使用git help可以查出常用的git命令  
使用git help -a可以查出所有的命令
### 2.config
配置git  
1). git gonfig -global user.name 'ying.chen'   配置全局的用户名  
2). git config -global user.emain '15702961083@163,com'   配置邮箱  
### 3.init  
初始化一个项目  
git init  
可以用git ls 查看生成的目录和文件  
### 4.diff  
使用git diff查看一个文件修改前和修改后的差别
git diff index.html 则查看index.html中的修改 
### 5.rename  
重命名一个git已经跟踪的文件  
style.css重命名为type.css  
使用git rm style.css 删除原来的。  
git add type.css  
则git会显示 rename：style.css -->type.css  
### 6.mv  
使用git mv 可以重命名一个文件或移动一个文件   
重新命名：
```
git mv style.css style-new.css  
git status  
renamed: style.css ->style-new.css
```  
移动文件  

```
git mkdir css
git mv style-new.css css/
git status
renamed: style-new.css ->css/style-new.css
```  
### 7.branch  
git branch 查看所有分支  
git branch ying.chen 创建分支  

### 8.checkout  
git checkout master 切换到主分支  
### 9.git log --oneline( --decorate) 
查看工作日志  
### 10.merge  
git merge master  
:wq 保存并退出  
### 11.conflict  
 冲突  merge conflict in index.html
 ### 重命名分支  
     git branch fix  
     git branch -m fix fix-new  
     把fix修改成fix-new  

    git branch -d fix-new  
    删除分支  
### 12.stash  
git stash 保存现场
git stash save '描述信息' 保存进度  
git stash list 查看工作进度  
git stash apply +工作代号  恢复保存的进度  
git stash drop +代号 删除工作进度  
### 13. log  
git log -- oneline 查看工作日志  
git log --oneline --5 查看最近五条  
git log --oneline --grep="index.html"  查看所有关于index的修改  
git log -oneline --before='3 days' 查看三天前的提交    
### 14.push  
git push origin master 推送到远端分支  
### 15.clone  
git clone 把远程版本库克隆到本地  
  
    
    
    
  
   
## git常用命令  
### 基础：  
    1.git init 初始化一个本地仓库  
    2.git clone url 克隆一个远端版本库到本地  
    3.git -rf .git 递归强制删除git版本库  
### 分支：  
    1.git branch 查看本地分支  
    2.git branch ying.chen 创建分支ying.chen  
    3.git checkout ying.chen 切换到ying.chen分支下  
    4.git checkout -b ying.chen 创建分支并切换到此分支下  
    5.git branch -d ying.chen 删除分支  
    6.git branch -D ying.chen 强制删除分支  
### 提交  
    1.git add -A/ git add . 将工作推到暂存区  
    2.git commit -m 'msg' 讲暂存区的内容提交到版本库中，Head指针挪到当前版本  
    3.git push 讲当前版本库中的文件提交到远程服务器  
### 回滚  
    1.git reset -hard $HEAD 版本回退到参数指定版本  
    2.git reset -soft $HEAD 只回退commit内容  
    3.git reset -mixed 回退库和暂存区内容  
### 远程  
    1.git remote -v 查看当前库与远程的哪个路径关联  
    2.git remote show origin 查看远程分支  
    3.git push origin :ying.chen 删除远端分支  
    4.git push origin ying.chen:ying.chen 冒号左边本地分支，冒号右边远端创建的分支  
    5.git push -set-upstream origin 为当前分支设置上传路径  
    6.git fetch Name 拉取远端分支 但不合并  
### 删除 
    1.git rm fileName 将本地库中file文件删除  
    2.git rm -cached file 从文件跟踪删除  
### 查看  
    1.git log -ongline 单行显示日志  
    2.git reflog 显示全部日志  
    3.git show $HEAD 查看HEAD指向的最新版本  
### 冲突  
    1.git stash 保存现场  
    2.git stach pop 恢复现场  
    3.git status 查看当前版本库里的情况  
    4.git add 推送修改后的冲突文件  
    5.git commit -m 'msg' 提交修改后的冲突文件


 

     


