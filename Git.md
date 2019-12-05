# Git 教程

## 参考
1. [Git详细教程-简书](https://www.jianshu.com/p/3d0d56d6f6d1)
2. [廖雪峰](https://www.liaoxuefeng.com/wiki/896043488029600)
3. [Git版本管理-莫烦](https://morvanzhou.github.io/tutorials/others/git/)
4. [Git参考手册](http://gitref.justjavac.com/basic/#status)

## Notes
1. 用户信息 git config user
```shell
git config --global user.name "wyndam"
git config --global user.email "only.night@qq.com"
```

2. 新建本地仓库 git init
```shell
git init
```

3.  添加文件到缓存
```shell
git status -s    # 查看我们的项目的当前状态
git add README hello.rb
git add .      # 添加所有文件
```

4. 显示已写入缓存与已修改但尚未写入缓存的改动的区别
```shell
git diff # 会以规范化的 diff 格式（一个补丁）显示自从你上次提交快照之后尚未缓存的所有更改。 
git diff --cached # 会告诉你有哪些内容已经写入缓存了。 也就是说，此命令显示的是接下来要写入快照的内容。
```

5.  记录缓存内容的快照
```shell
git commit -m 'my hola mundo changes'
```

6. 取消缓存

```shell
git reset HEAD -- hello.rb 
```

7. 回退版本
```shell
git reset --hard c503c
```

8. 重命名
```shell
git mv old_filename new_filename
```

## Angular 规范的 Commit message 格式
每次提交，Commit message 都包括三个部分：Header，Body 和 Footer。

> [type] [(scope)]: [subject] 
> //
> [body]
> //
> [footer]

其中，Header 是必需的，Body 和 Footer 可以省略。

### Header

Header 部分只有一行，包括三个字段：type（必需）、scope（可选）和 subject（必需）。

**type** 用于说明 commit 的类别，只允许使用下面7个标识。

- **feat** 新功能（feature）
- **fix** 修补bug
- **docs** 文档（documentation）
- **style** 格式（不影响代码运行的变动）
- **refactor** 重构（即不是新增功能，也不是修改bug的代码变动）
- **test** 增加测试
- **chore** 构建过程、辅助工具的变动
- **perf** 提高性能

如果 **type** 为 **feat** 和 **fix**，则该 commit 将肯定出现在 Change log 之中。

**scope** 用于说明 commit 影响的范围，比如数据层、控制层、视图层等等，视项目不同而不同。

**subject** 是 commit 目的的简短描述，不超过50个字符。

- 以动词开头，使用第一人称现在时，比如 change，而不是 changed 或 changes
- 第一个字母大写
- 结尾不加句号

### [Commitizen](https://github.com/commitizen/cz-cli)

####  Install 

```shell
npm install commitizen -g
```

#### Initialize your project

```shell
commitizen init cz-conventional-changelog --save-dev --save-exact
```

#### Now

Simply use `git cz` instead of `git commit` when committing.

```shell
git cz --amend  # edit the commit message
```



## Ignoring files ----- .gitignore
See: [Learning How to Git: Ignoring Files and Folders using GitIgnore](https://medium.com/@haydar_ai/learning-how-to-git-ignoring-files-and-folders-using-gitignore-177556afdbe3)

Create a .gitignore file in repository, and write like that:

```shell
# Ignore file or folder for optimization framework
SVN/    # folder
__pycache__/    # folder
Optres.txt
Statistics.txt
x_mopta.txt

# C extensions
*.so

# Spyder project settings
.spyderproject
.spyproject
```

https://www.gitignore.io/ ---- Create useful files 