## Git 常用操作总结

### 1. 初始化 Git 仓库
```sh
git init
```
在当前目录创建一个 Git 仓库。

### 2. 克隆远程仓库
```sh
git clone <仓库地址>
```
从远程拉取已有仓库到本地。

### 3. 查看仓库状态
```sh
git status
```
显示工作区、暂存区的状态。

### 4. 添加文件到暂存区
```sh
git add <文件名>  # 添加单个文件
git add .         # 添加所有更改的文件
```

### 5. 提交修改
```sh
git commit -m "提交信息"
```
将暂存区内容提交到本地仓库。

### 6. 创建分支
```sh
git branch <分支名>
```

### 7. 创建并切换到新分支
```sh
git checkout -b <分支名>
```
等同于：
```sh
git branch <分支名>
git checkout <分支名>
```

### 8. 查看分支
```sh
git branch
```
显示所有本地分支，`*` 标记当前所在分支。

### 9. 切换分支
```sh
git checkout <分支名>
```

### 10. 合并分支
```sh
git checkout main  # 切换到主分支
git merge <被合并的分支名>
```

### 11. 删除分支
```sh
git branch -d <分支名>  # 删除本地分支
git push origin --delete <分支名>  # 删除远程分支
```

### 12. 远程仓库管理
```sh
git remote add origin <远程仓库地址>
git remote -v  # 查看远程仓库
```

### 13. 推送代码到远程仓库
```sh
git push origin <分支名>
```
第一次推送需要：
```sh
git push -u origin <分支名>
```

### 14. 拉取远程代码
```sh
git pull origin <分支名>
```

### 15. 创建 SSH 密钥对（用于 Git 认证）
```sh
ssh-keygen -t rsa -b 4096 -C "your_email@example.com"
```
然后将 `~/.ssh/id_rsa.pub` 添加到 GitHub/GitLab 的 SSH Keys 中。

### 16. 撤销 `git add`
```sh
git reset HEAD <文件名>
```

### 17. 撤销最近一次提交（保留修改）
```sh
git reset --soft HEAD~1
```

### 18. 回退到指定版本
```sh
git reset --hard <提交ID>
```

### 19. 查看提交历史
```sh
git log  # 显示完整日志
git log --oneline  # 仅显示提交摘要
```

### 20. 解决合并冲突
1. 打开冲突文件，手动编辑 `<<<<<<<` 和 `>>>>>>>` 之间的内容。
2. 标记冲突已解决：
   ```sh
   git add <冲突文件>
   ```
3. 提交合并结果：
   ```sh
   git commit -m "解决合并冲突"
   ```

### 21. 忽略文件（`.gitignore`）
```plaintext
# 忽略 VSCode 相关文件
.vscode/

# 忽略编译生成的二进制文件
*.exe
*.obj

# 忽略 Python 缓存文件
__pycache__/
*.pyc
```
然后提交 `.gitignore` 文件：
```sh
git add .gitignore
git commit -m "添加 .gitignore 文件"
```

### 22. 配置 Git 记住密码
```sh
git config --global credential.helper store
```

### 23. 强制推送（慎用）
```sh
git push -f origin <分支名>
```

---

## **Git 常用命令速查表**
| 操作            | 命令                                                    |
| --------------- | ------------------------------------------------------- |
| 初始化仓库      | `git init`                                              |
| 克隆仓库        | `git clone <仓库地址>`                                  |
| 查看状态        | `git status`                                            |
| 添加文件        | `git add <文件名>`                                      |
| 提交修改        | `git commit -m "提交信息"`                              |
| 创建分支        | `git branch <分支名>`                                   |
| 创建并切换分支  | `git checkout -b <分支名>`                              |
| 切换分支        | `git checkout <分支名>`                                 |
| 合并分支        | `git merge <分支名>`                                    |
| 删除分支        | `git branch -d <分支名>`                                |
| 推送到远程      | `git push origin <分支名>`                              |
| 拉取远程代码    | `git pull origin <分支名>`                              |
| 生成 SSH 密钥对 | `ssh-keygen -t rsa -b 4096 -C "your_email@example.com"` |
| 查看提交历史    | `git log --oneline`                                     |
| 解决合并冲突    | `git add <文件>` `git commit -m "解决冲突"`             |
| 忽略文件        | `.gitignore`                                            |