
### 初配置
- ```git config --global user.name "USERNAME"```
- ```git config --global user.email "EMAIL_ADDRESS"```
- ```git config --global color.ui auto```
- ```less ~/.gitconfig```

### 微调 
> *keyword* : <small>macOS, 中文文件名</small>

- ```git config --global core.quotePath false``` 
- ```git config --global core.precomposeunicode true```

### 建联系
- ```ssh-keygen -t rsa -C "EMAIL_ADDRESS"```
	- ```less ~/.ssh/id_rsa.pub``` 将相应内容复制至 Github 的 SSH KEY 处
	- 此命令最好置于用户主目录下
- ```ssh -T git@github.com``` 测试能否正常连通

### 首Repo
- 建立后 复制其 Git 地址 并 ```git clone``` 之 
- 此时可开始作一些操作 <small>(写/改代码, 写文档 etc.</small>
- 察状态 加文件
	- ```git add``` 要推至 *Github* 的文件
- 推文件
	- ```git commit -m “WHAT_YOU_WANT_TO_SAY”```
	- **```git push```**

### 察状态

| command | detail / usage |
|---|---|
| ```git log [-p] [FILENAME] [--graph] ``` | 察看提交记录 <small>( 加 `-p` 可察详, 类似 ```git diff```</small> |
| ```git status``` | 工作区当前状态 以及一些建议 |
| ```git diff [HEAD]``` | 察看更改 <small>(未add前)</small> 若入暂存区则需加 *HEAD* |

### 常用

| command | detail / usage |
|---|---|
| ```git commit -m 简短介绍```  | \ |
| ```git commit``` | 详尽记录 <small>(头行简述 自第三行详述)</small> |
| ```git add FILENAME``` | 须键入于每次修改后 |
| ```git rm FILENAME``` | 将其丢出暂存区 |
| ```git push``` | 推至 *Github* |

### 分支

| command | detail / usage |
|---|---|
| ```git checkout BRANCH_NAME``` | 切换分支 |
| ```git checkout -b BRANCH_NAME``` | 仅执行 *若无,新建并切换之* |
| ```git branch -d BRANCH_NAME``` | 删除分支 |

### 分支进阶

| command | detail / usage |
|---|---|
| ```git reset --hard HASH_VALUE``` | *穿越至* 对应 Hash 值的历史 <small>(记得回到 master 分支</small> |
| ```git reflog [--all]``` | 此项存有 完整的操作历史 |
