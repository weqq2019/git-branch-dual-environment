# git-branch-dual-environment
📘双系统 Git 分支操作指南


## 项目简介
这是一个学习如何在双系统环境（如 Windows 和 WSL）中操作 Git 分支的指南。通过该项目，你将掌握在不同操作系统上使用 Git 的分支管理、合并、冲突解决以及同步操作。

## 主要内容
- 如何在不同系统（Windows 和 WSL）中使用 Git。
- 管理和同步远程分支。
- 合并、处理冲突以及版本回滚。
- 安全管理代码，不使用 `--force` 等危险操作。

## 环境需求
- Windows 系统（或其他系统）
- WSL（Windows Subsystem for Linux）或其他 Linux 环境
- 安装了 Git 的终端

## 使用指南

1. **克隆仓库**
   - 从远程仓库克隆项目到本地：
     ```bash
     git clone <repository_url>
     cd <repository_name>
     ```
   - 替换 `<repository_url>` 为你的远程仓库地址，`<repository_name>` 为你的项目文件夹名称。

2. **创建新分支**
   - 在本地创建一个新的 Git 分支并切换到该分支：
     ```bash
     git checkout -b <new_branch_name>
     ```
   - `<new_branch_name>` 可以是你要创建的新功能、修复或其他任务的名称，例如 `feature/login-page`。

3. **提交更改**
   - 在本地修改文件后，添加更改到暂存区并提交：
     ```bash
     git add <file_name>  # 添加单个文件
     git add .  # 添加所有更改的文件
     git commit -m "描述你的更改内容"
     ```
   - 提交信息需要简洁且有意义，描述此次提交的修改内容。

4. **推送到远程分支**
   - 将本地的修改推送到远程仓库对应的分支：
     ```bash
     git push origin <branch_name>
     ```
   - 确保你推送到合适的远程分支，`<branch_name>` 通常是当前工作分支。

5. **合并分支**
   - 在 `master` 或其他目标分支上合并 `develop` 或功能分支：
     ```bash
     git checkout master  # 切换到目标分支
     git merge <branch_name>  # 合并指定分支
     ```
   - 如果出现冲突，Git 会提示解决冲突。

6. **处理冲突**
   - 如果合并时出现冲突，使用编辑器打开冲突文件（如 VSCode），手动解决冲突。处理完后：
     ```bash
     git add <file_name>
     git commit -m "解决了冲突"
     ```

7. **回到主分支并更新远程仓库**
   - 完成所有更改后，推送合并后的 `master` 分支到远程仓库：
     ```bash
     git push origin master
     ```

8. **同步远程更新到本地**
   - 当其他人更新了远程仓库时，你可以使用以下命令获取最新的更改并合并到当前分支：
     ```bash
     git fetch origin
     git pull origin master  # 或者 develop 分支等
     ```

9. **临时保存未完成的工作**
   - 如果你需要切换分支但不想提交当前工作，可以使用 `git stash` 暂存工作：
     ```bash
     git stash
     ```
   - 当你需要恢复这些工作时，运行：
     ```bash
     git stash pop
     ```


