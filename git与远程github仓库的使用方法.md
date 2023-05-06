# git与远程github仓库的使用方法

## 1、创建本地仓库添加任意文件
![image-20230506110921700](https://user-images.githubusercontent.com/63906638/236601844-db459cc0-4bdb-447e-85cb-781ba7b07185.png)

## 2、本地仓库常用命令（管理本地仓库）

git init   //将项目通过git初始化

git add  +文件名    如（git add 1.md）    //将指定文件添加到暂存区

git add .      //添加所有修改到暂存区

git commit -m +提交的备注     如（git commit -m "my fisrt commit"）

git status   //查看当前仓库文件的管理状态

git log   //查看仓库的历史变化日志信息

git branch +分支名	如（git branch newbranch）	//创建新的分支

git checkout +分支名   如（git checkout newbranch）	//切换到newbranch分支

git checkout  +文件名    如（git checkout 1.md）   //用暂存区的文件覆盖掉未托管的文件，即放弃工作区中某个文件的修改

git reset --hard +历史提交的commit如（git reset --hard 3f84ae6245913349b742907a1c46f722dd8f309b）	//将工作区和暂存区的内容回退到指定的历史记录

## 3、远程仓库管理及代码上传 

***①.空仓库***

git remote add origin +远程仓库地址    如）（git remote add orign  https://github.com/qingwuzhou/distortion-correction.git）   //链接到远程仓库地址并给远程仓库取了别名orign

git push origin master     //将master分支提交到远程地址

***②.非空仓库***

远程非空仓库的关联，就要涉及到2个不同项目的关联了；得先将远程的代码合并下来，才能提交；我们先假设项目已经通过git管理了。缺少关联push远程仓库的步骤讲：
关联远程仓库：git remote add origin (仓库地址)
git pull origin master --allow-unrelated-histories（意思是2个不同项目的没关联提交允许拉取合并）
git push origin master（push成功，完工...）
