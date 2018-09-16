### Info 

| Author | Platform | Link |
| :---: | --- | --- |
| *Gergely Nemeth* | [blog.risingstack.com](https://blog.risingstack.com) | [Yarn vs npm - which node package manager to use in 2018?](https://blog.risingstack.com/yarn-vs-npm-node-js-package-managers/) |

-----------------

### Purpose 
- 我主 *Python*。
- 此文件只是為記錄 Node 相關的包管理器的基礎知識 <small>( 至少知道怎麼下載包 XD )</small>。

### Lockfile
> It does more if comparing with the Python’s ```pipenv```.

- Both got ```package.json``` 
- But *yarn* provides **dependency management** <small>( they call it ```Workspace``` )</small>.
- The ```Workspace``` feature was powered by [Lerna](https://github.com/lerna/lerna).

### Cache 
- If ya installed a package which u installed before, it’ll just use the old one, thus ***cache***.
- The cache folder is here: ```~/.yarn-cache```, <br>each version of the package’ll be put into different folders with prefixes.

### Install 
- The author *recommended* this: ```brew update && brew install yarn```

<hr>

**That’s all 😉**.

