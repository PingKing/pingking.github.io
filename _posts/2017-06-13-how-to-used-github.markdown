---
layout: post
category: "other"
title:  "人生什么更重要？[测试]"
tags: [阅读,人生]
---
### github入门

 
	Workspace：工作区
	Index / Stage：暂存区
	Repository：仓库区（或本地仓库）
	Remote：远程仓库
在当前目录新建一个Git代码库
$ git init
# 新建一个目录，将其初始化为Git代码库
$ git init [project-name]
# 下载一个项目和它的整个代码历史
$ git clone [url]

# 显示当前的Git配置
$ git config --list
# 编辑Git配置文件
$ git config -e [--global]
# 设置提交代码时的用户信息
$ git config [--global] user.name "[name]"
$ git config [--global] user.email "[email address]"
# 添加指定文件到暂存区
$ git add [file1] [file2] ...
# 添加指定目录到暂存区，包括子目录
$ git add [dir]
# 添加当前目录的所有文件到暂存区
$ git add .
# 添加每个变化前，都会要求确认
# 对于同一个文件的多处变化，可以实现分次提交
$ git add -p
# 删除工作区文件，并且将这次删除放入暂存区
$ git rm [file1] [file2] ...
# 停止追踪指定文件，但该文件会保留在工作区
$ git rm --cached [file]
# 改名文件，并且将这个改名放入暂存区
$ git mv [file-original] [file-renamed]
# 提交暂存区到仓库区
$ git commit -m [message]

# 提交暂存区的指定文件到仓库区
$ git commit [file1] [file2] ... -m [message]
# 提交工作区自上次commit之后的变化，直接到仓库区
$ git commit -a
# 提交时显示所有diff信息
$ git commit -v
# 使用一次新的commit，替代上一次提交
# 如果代码没有任何新变化，则用来改写上一次commit的提交信息
$ git commit --amend -m [message]
# 重做上一次commit，并包括指定文件的新变化
$ git commit --amend [file1] [file2] ...
# 列出所有本地分支
$ git branch
# 列出所有远程分支
$ git branch -r
# 列出所有本地分支和远程分支
$ git branch -a
# 新建一个分支，但依然停留在当前分支
$ git branch [branch-name]
# 新建一个分支，并切换到该分支
$ git checkout -b [branch]
# 新建一个分支，指向指定commit
$ git branch [branch] [commit]
# 新建一个分支，与指定的远程分支建立追踪关系
$ git branch --track [branch] [remote-branch]
# 切换到指定分支，并更新工作区
$ git checkout [branch-name]
# 切换到上一个分支
$ git checkout -
# 建立追踪关系，在现有分支与指定的远程分支之间
$ git branch --set-upstream [branch] [remote-branch]
# 合并指定分支到当前分支
$ git merge [branch]
# 选择一个commit，合并进当前分支
$ git cherry-pick [commit]
# 删除分支
$ git branch -d [branch-name]
# 删除远程分支
$ git push origin --delete [branch-name]
$ git branch -dr [remote/branch]
# 列出所有tag
$ git tag
# 新建一个tag在当前commit
$ git tag [tag]

# 新建一个tag在指定commit
$ git tag [tag] [commit]
# 删除本地tag
$ git tag -d [tag]
# 删除远程tag
$ git push origin :refs/tags/[tagName]
# 查看tag信息
$ git show [tag]
# 提交指定tag
$ git push [remote] [tag]
# 提交所有tag
$ git push [remote] --tags
# 新建一个分支，指向某个tag
$ git checkout -b [branch] [tag]
# 显示有变更的文件
$ git status
# 显示当前分支的版本历史
$ git log
# 显示commit历史，以及每次commit发生变更的文件
$ git log --stat
# 搜索提交历史，根据关键词
$ git log -S [keyword]
# 显示某个commit之后的所有变动，每个commit占据一行
$ git log [tag] HEAD --pretty=format:%s
# 显示某个commit之后的所有变动，其"提交说明"必须符合搜索条件
$ git log [tag] HEAD --grep feature
# 显示某个文件的版本历史，包括文件改名
$ git log --follow [file]
$ git whatchanged [file]
# 显示指定文件相关的每一次diff
$ git log -p [file]
# 显示过去5次提交
$ git log -5 --pretty --oneline
# 显示所有提交过的用户，按提交次数排序
$ git shortlog -sn
# 显示指定文件是什么人在什么时间修改过
$ git blame [file]
# 显示暂存区和工作区的差异
$ git diff
# 显示暂存区和上一个commit的差异
$ git diff --cached [file]
# 显示工作区与当前分支最新commit之间的差异
$ git diff HEAD

# 显示两次提交之间的差异
$ git diff [first-branch]...[second-branch]
# 显示今天你写了多少行代码
$ git diff --shortstat "@{0 day ago}"
# 显示某次提交的元数据和内容变化
$ git show [commit]
# 显示某次提交发生变化的文件
$ git show --name-only [commit]
# 显示某次提交时，某个文件的内容
$ git show [commit]:[filename]
# 显示当前分支的最近几次提交
$ git reflog
# 下载远程仓库的所有变动
$ git fetch [remote]
# 显示所有远程仓库
$ git remote -v
# 显示某个远程仓库的信息
$ git remote show [remote]
# 增加一个新的远程仓库，并命名
$ git remote add [shortname] [url]
# 取回远程仓库的变化，并与本地分支合并
$ git pull [remote] [branch]
# 上传本地指定分支到远程仓库
$ git push [remote] [branch]
# 强行推送当前分支到远程仓库，即使有冲突
$ git push [remote] --force
# 推送所有分支到远程仓库
$ git push [remote] --all
# 恢复暂存区的指定文件到工作区
$ git checkout [file]
# 恢复某个commit的指定文件到暂存区和工作区
$ git checkout [commit] [file]
# 恢复暂存区的所有文件到工作区
$ git checkout .
# 重置暂存区的指定文件，与上一次commit保持一致，但工作区不变
$ git reset [file]
# 重置暂存区与工作区，与上一次commit保持一致
$ git reset --hard
# 重置当前分支的指针为指定commit，同时重置暂存区，但工作区不变
$ git reset [commit]
# 重置当前分支的HEAD为指定commit，同时重置暂存区和工作区，与指定commit一致
$ git reset --hard [commit]

# 重置当前HEAD为指定commit，但保持暂存区和工作区不变
$ git reset --keep [commit]
# 新建一个commit，用来撤销指定commit
# 后者的所有变化都将被前者抵消，并且应用到当前分支
$ git revert [commit]
# 暂时将未提交的变化移除，稍后再移入
$ git stash
$ git stash pop
# 生成一个可供发布的压缩包
$ git archive

Sublime常用快捷键：
掌握基本的代码编辑器的快捷键，能让你打码更有效率,刚开始可能不大记得住，多敲几次就能熟悉并使用它
精华键 :
Ctrl+Shift+P：打开命令面板 
Ctrl+P：搜索项目中的文件 
Ctrl+G：跳转到第几行 
Ctrl+W：关闭当前打开文件 
Ctrl+Shift+W：关闭所有打开文件 
Ctrl+Shift+V：粘贴并格式化 
Ctrl+D：选择单词，重复可增加选择下一个相同的单词 
Ctrl+L：选择行，重复可依次增加选择下一行 
Ctrl+Shift+L：选择多行 
Ctrl+Shift+Enter：在当前行前插入新行 
Ctrl+X：删除当前行 
Ctrl+M：跳转到对应括号 
Ctrl+U：软撤销，撤销光标位置 
Ctrl+J：选择标签内容 
Ctrl+F：查找内容 
Ctrl+Shift+F：查找并替换 
Ctrl+H：替换 
Ctrl+R：前往 method 
Ctrl+N：新建窗口 
Ctrl+K+B：开关侧栏 
Ctrl+Shift+M：选中当前括号内容，重复可选着括号本身 
Ctrl+F2：设置/删除标记 
Ctrl+/：注释当前行 
Ctrl+Shift+/：当前位置插入注释 
Ctrl+Alt+/：块注释，并Focus到首行，写注释说明用的 
Ctrl+Shift+A：选择当前标签前后，修改标签用的 
F11：全屏 
Shift+F11：全屏免打扰模式，只编辑当前文件 
Alt+F3：选择所有相同的词 
Alt+.：闭合标签 
Alt+Shift+数字：分屏显示 
Alt+数字：切换打开第N个文件 
Shift+右键拖动：光标多不，用来更改或插入列内容 
鼠标的前进后退键可切换Tab文件 
按Ctrl，依次点击或选取，可需要编辑的多个位置 
按Ctrl+Shift+上下键，可替换行

选择类 :

Ctrl+D 选中光标所占的文本，继续操作则会选中下一个相同的文本。 
Alt+F3 选中文本按下快捷键，即可一次性选择全部的相同文本进行同时编辑。举个栗子：快速选中并更改所有相同的变量名、函数名等。 
Ctrl+L 选中整行，继续操作则继续选择下一行，效果和 Shift+↓ 效果一样。 
Ctrl+Shift+L 先选中多行，再按下快捷键，会在每行行尾插入光标，即可同时编辑这些行。 
Ctrl+Shift+M 选择括号内的内容（继续选择父括号）。举个栗子：快速选中删除函数中的代码，重写函数体代码或重写括号内里的内容。 
Ctrl+M 光标移动至括号内结束或开始的位置。 
Ctrl+Enter 在下一行插入新行。举个栗子：即使光标不在行尾，也能快速向下插入一行。 
Ctrl+Shift+Enter 在上一行插入新行。举个栗子：即使光标不在行首，也能快速向上插入一行。 
Ctrl+Shift+[ 选中代码，按下快捷键，折叠代码。 
Ctrl+Shift+] 选中代码，按下快捷键，展开代码。 
Ctrl+K+0 展开所有折叠代码。 
Ctrl+← 向左单位性地移动光标，快速移动光标。 
Ctrl+→ 向右单位性地移动光标，快速移动光标。 
shift+↑ 向上选中多行。 
shift+↓ 向下选中多行。 
Shift+← 向左选中文本。 
Shift+→ 向右选中文本。 
Ctrl+Shift+← 向左单位性地选中文本。 
Ctrl+Shift+→ 向右单位性地选中文本。 
Ctrl+Shift+↑ 将光标所在行和上一行代码互换（将光标所在行插入到上一行之前）。 
Ctrl+Shift+↓ 将光标所在行和下一行代码互换（将光标所在行插入到下一行之后）。 
Ctrl+Alt+↑ 向上添加多行光标，可同时编辑多行。 
Ctrl+Alt+↓ 向下添加多行光标，可同时编辑多行。

编辑类 : 
Ctrl+J 合并选中的多行代码为一行。举个栗子：将多行格式的CSS属性合并为一行。 
Ctrl+Shift+D 复制光标所在整行，插入到下一行。 
Tab 向右缩进。 
Shift+Tab 向左缩进。 
Ctrl+K+K 从光标处开始删除代码至行尾。 
Ctrl+Shift+K 删除整行。 
Ctrl+/ 注释单行。 
Ctrl+Shift+/ 注释多行。 
Ctrl+K+U 转换大写。 
Ctrl+K+L 转换小写。 
Ctrl+Z 撤销。 
Ctrl+Y 恢复撤销。 
Ctrl+U 软撤销，感觉和 Gtrl+Z 一样。 
Ctrl+F2 设置书签 
Ctrl+T 左右字母互换。 
F6 单词检测拼写

搜索类 : 
Ctrl+F 打开底部搜索框，查找关键字。 
Ctrl+shift+F 在文件夹内查找，与普通编辑器不同的地方是sublime允许添加多个文件夹进行查找，略高端，未研究。 
Ctrl+P 打开搜索框。举个栗子：1、输入当前项目中的文件名，快速搜索文件，2、输入@和关键字，查找文件中函数名，3、输入：和数字，跳转到文件中该行代码，4、输入#和关键字，查找变量名。 
Ctrl+G 打开搜索框，自动带：，输入数字跳转到该行代码。举个栗子：在页面代码比较长的文件中快速定位。 
Ctrl+R 打开搜索框，自动带@，输入关键字，查找文件中的函数名。举个栗子：在函数较多的页面快速查找某个函数。 
Ctrl+： 打开搜索框，自动带#，输入关键字，查找文件中的变量名、属性名等。 
Ctrl+Shift+P 打开命令框。场景栗子：打开命名框，输入关键字，调用sublime text或插件的功能，例如使用package安装插件。 
Esc 退出光标多行选择，退出搜索框，命令框等。 
显示类 
Ctrl+Tab 按文件浏览过的顺序，切换当前窗口的标签页。 
Ctrl+PageDown 向左切换当前窗口的标签页。 
Ctrl+PageUp 向右切换当前窗口的标签页。 
Alt+Shift+1 窗口分屏，恢复默认1屏（非小键盘的数字） 
Alt+Shift+2 左右分屏-2列 
Alt+Shift+3 左右分屏-3列 
Alt+Shift+4 左右分屏-4列 
Alt+Shift+5 等分4屏 
Alt+Shift+8 垂直分屏-2屏 
Alt+Shift+9 垂直分屏-3屏 
Ctrl+K+B 开启/关闭侧边栏。 
F11 全屏模式 
Shift+F11 免打扰模式


