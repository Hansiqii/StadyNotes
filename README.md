# 所有的学习笔记的整理和感悟都在这里！😊

## 1 关于这个仓库的维护和使用



### 登录

```bash
git config --global user.name "Your Name"
git config --global user.email "you@example.com"
```



### 克隆主仓库（包含子模块）

```bash
git clone https://github.com/yourusername/StadyNotes.git
cd StadyNotes
```



### 初始化子模块

```
git submodule update --init --recursive
```

如果主仓库包含多个子模块，这条命令会自动拉取所有子模块的内容



### 增加和修改内容

修改主仓库中的文件

```bash
git add .
git commit -m "Update main repository"
git push
```



修改子模块

```bash
cd path/to/submodule
git add .
git commit -m "Update submodule content"
git push
```



### 添加子模块

先建好子模块地址

```
git submodule add https://github.com/yourusername/new-submodule.git new-submodule-folder
```

`https://github.com/yourusername/new-submodule.git` 是子模块的远程地址。

`new-submodule-folder` 是子模块在主仓库中的文件夹名称。



提交子模块的变更到主仓库

```
git add .gitmodules new-submodule-folder
git commit -m "Add new submodule"
git push
```





### 删除子模块

如果一个子模块不再需要，可以按照以下步骤删除：

1. 取消子模块的初始化：

   bash

   复制

   ```
   git submodule deinit -f path/to/submodule
   ```

2. 删除子模块的跟踪记录：

   bash

   复制

   ```
   git rm -f path/to/submodule
   ```

3. 删除本地子模块的文件夹（可选）：

   bash

   复制

   ```
   rm -rf .git/modules/path/to/submodule
   ```

提交变更：

```
git commit -m "Remove submodule"
git push
```