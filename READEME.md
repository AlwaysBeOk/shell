## 流行工具&框架
## shell
###	什么是shell
- 在计算机科学中，Shell俗称壳，用来区别于Kernel（核），是指“提供使用者使用界面”的软件（命令解析器）。
它类似于DOS下的command和后来的cmd.exe。它接收用户命令，然后调用相应的应用程序。

![Alt text](./pic/1.png)
### shell分类
- 图形界面shell：通过提供友好的可视化界面，调用相应应用程序，
  如windows系列操作系统，Linux系统上的图形化应用程序Unity、KDE等。
- 命令行shell：通过键盘输入特定命令的方式，调用相应的应用程序，
  如windows系统的cmd.exe、Windows PowerShell，
  Linux系统的Bourne shell ( sh)、Bourne Again shell ( bash)、zsh等
### 认识bash这个shell
- 在window系统下使用bash，需要一个软件，这个软件模拟集成了bash大部分命令。
各个 shell 的功能都差不多， Linux 默认使用 bash ，所以我们主要学习bash的使用。
### bash命令格式
命令 [-options] [参数]，如：mkdir blog   如果有<>表示必须要有这个参数,[]可选参数
查看帮助：--help是命令的一个参数,命令后面加上 --help 或者 -h , -h是--help的缩写形式 可以打开命令的一个说明，说明中有这个命令的参数的具体的解释
### bash常见命令
- pwd (Print Working Directory) 查看当前目录

- cd (Change Directory) 
   切换目录，如 cd etc
   寻找上级目录 cd ..
   在寻找目录的的时候----tab键去补全
   也可以通过 cd a/b/c 一个路径的形式去进入目录

- ls (List) 查看当前目录下内容，如 ls -al

- mkdir (Make Directory) 创建目录，如 mkdir blog

- touch 创建文件，如 touch index.html

- cat 查看文件全部内容，如 cat index.html

- rm (remove) 删除文件，如 rm index.html、rm -rf  blog(慎用-删除非空)

- rmdir (Remove Directory) 删除文件夹，只能删除空文件夹，不常用

- mv (move) 移动文件或重命名，如 mv index.html ./demo/index.html

- cp (copy) 复制文件，cp index.html ./demo/index.html

- head 查看文件前几行，如 head -5 index.html

- tail 查看文件后几行 –n，如 tail index.html、tail -n  5 index.html 

- tab 自动补全，连按两次会将所有匹配内容显示出来

- history 查看操作历史

- curl 网络请求，如curl http://www.baidu.com

-ps axu | grep tomcat | awk '{print $2}' | xargs kill -9

## vi编辑器
### 什么是vi编辑器
- 如同Windows下的记事本，vi编辑器是Linux下的标配，通过它我们可以创建、编辑文件。
  它是一个随系统一起安装的文本编辑软件。
### 三种模式
- vi编辑器提供了3种模式，分别是命令模式、插入模式、底行模式，每种模式下用户所能进行的操作是不一样的。
3种模式的切换如下图所示：

![Alt text](./pic/2.png)

### 使用vi编辑器
	a) 打开/创建文件， vi 文件路径
	b) 底行模式 :w保存，:w filenme另存为
	c) 底行模式 :q退出
	d) 底行模式 :wq保存并退出
	e) 底行模式 :e! 撤销更改，返回到上一次保存的状态
	f) 底行模式 :q! 不保存强制退出
	g) 底行模式 :set nu 设置行号
	h) 命令模式 ZZ（大写）保存并退出
	i) 命令模式 u辙销操作，可多次使用
	j) 命令模式 dd删除当前行
	k) 命令模式 yy复制当前行
	l) 命令模式 p 粘贴内容
	m) 命令模式 ctrl+f向前翻页
	n) 命令模式 ctrl+b向后翻页
	o) 命令模式 i进入编辑模式，当前光标处插入
	p) 命令模式 a进入编辑模式，当前光标后插入
	q) 命令模式 A进入编辑模式，光标移动到行尾
	r) 命令模式 o进入编辑模式，当前行下面插入新行
	s) 命令模式 O进入编辑模式，当前行上面插入新行
当我们处在编辑模式的情况下，和我们在Windows编辑器的使用相似。

### 为什么需要版本管理工具？
git、svn，

### 什么是Git?
  - Git是一款源代码管理工具(版本控制工具)
    - 我们写的代码需要使用Git进行管理。
  1.0是稳定
  2.0加了新功能
  - 源代码有必要管理起吗？
  - 有必要，因为人工的去处理不同的版本，做相应备份会很麻烦。
  - svn,vss,vcs,tfs.....
  -Git是linux之父当年为了维护linux---linus之前也是手动维护合并把文件发给Linus
  - BitKeeper(收费)
  - 有人想破解(不给提供免费使用)
  - linus自己写了一个版本管理的工具（Git）


### 分布式版本管理工具，集中式
  - git属于分布式
  - svn集中式

### git安装

### git初始化一个仓库
  - 其实就是创建了一个.git隐藏目录
  - 命令:` git init `;
    + 想在哪个目录创建.git目录，就是哪个目录打开工具然后写命令.
    + 一般是在项目的根目录执行这个命令.


### 自报家门
  - 配置用户名 : `git config user.name "testName"`
  - 配置邮箱   : `git config user.email "test@sina.com"`
  - 上面这两条命令是在设置我当前目录里面的用户名和邮箱
  - 查看配置信息: `git config --list`
  - 全局设置 :`git config --global user.name [username]`
  - 全局设置 :`git config --global user.email [email]`


### 把代码提交到仓库中
  - 1.先把代码添加到暂存区(就相当于放到仓库门口)
    + 命令:`git add 文件路径`
    + 示例:`git add ./reademe.md`
    + 可以使用`git add .`这个命令，批量把当前目录下所有修改过的文件添加到暂存区。

  - 2.把暂存区的文件提交仓库里
    + 命令: `git commit -m "注释" `
    + 示例: `git commit -m "我们添加了一个新的功能"`
    + -m 表示指定一个字符串，作为提交的说明(相当于注释);

  - 合并add 与commit 命令
    + `git commit -a -m "这是使用合并添加与提交的操作"`;
    + 这里-a参数表明把所有修改后的文件一起添加到暂存区.(只是对修改后的文件有效，对于新添加的文件没有作用)
    + 在提交到仓库里面


### 查看工作区状态
  - 命令:`git status`


### 添加忽略文件
  - 在项目中有一些文件是不需要提交的,我们需要把它忽略掉
  - 需要在.git文件夹所在目录新建一个名为.gitignore的文件
    然后在这个文件中写上需要被忽略的文件的路径。
    示例: /css/a.css
        : /css/*.css
        : /a.html


### 比对文件差异
  - 命令: `git diff`
    + 用来比较暂存区文件内容与工作区文件内容的区别
    + 如果暂存区没有文件，就会将工作与代码与最近一次提交对比
  - 命令：`git diff --cached`
  - 对比之前某两次提交的文件的差异
    + 命令:`git diff [版本号1] [版本号2] [想比较的文件路径]`

### 查看日志
  - 命令:`git log`,可以查看每一次提交的日志
  - 命令:`git log --oneline` 表示使用简洁的形式输出提交日志


### 版本回退
  - 命令:`git reset --hard Head~1`
    + 这是将代码回退到上上一次提交时的状态
  - 命令:`git reset --hard Head~2`
    + 回退到上上上次
  - 命令:`git reset --hard Head~0`
    + 回退到上次提交时的状态,~0可以省略

  - 命令:`git reset --hard 版本号`
    + 通过每次提交时生成的版本号来回退版本

  - 通过`git reflog`命令可以查看之前所有版本切换的操作记录，可以通过这个命令得到的版本号回退到指定的版本。

