# GitHub 使用教程（初学者完整版）

> 本教程面向零基础初学者，带你从了解 Git/GitHub 到参与开源项目。

---

## 一、什么是 GitHub？

GitHub 是一个基于 Git 的代码托管平台，简单说就是**存放代码的云端仓库**。你可以把它理解为代码界的"Google 云盘"，但它远不止存储这么简单：

- **版本控制**：记录每一次代码修改，随时可以回退到任意版本
- **协作**：多人同时开发同一项目，互不干扰
- **开源社区**：全球最大的程序员社交平台，数亿个项目托管在上面

### GitHub 上的核心社交元素

| 功能 | 说明 |
|------|------|
| **Star（星星）** | 给项目点赞，表示收藏或关注。相当于书签 |
| **Fork（复刻）** | 把别人的项目复制一份到自己的 GitHub 账号下 |
| **Watch（关注）** | 关注项目动态，有新的 Issue/PR 会收到通知 |
| **Profile（个人主页）** | 你的 GitHub 名片，展示你的仓库、贡献图、个人介绍 |
| **Contribution Graph** | 你的"绿点矩阵"，每次提交都会点亮一个小绿点 |

新手小贴士：**多 Star 你喜欢的项目**，这是 GitHub 上最基础的社交方式。

---

## 二、准备工作

### 2.1 注册 GitHub 账号

1. 打开 https://github.com
2. 点击右上角 **Sign up**
3. 输入用户名、邮箱、密码
4. 验证邮箱（去收件箱点击确认链接）

> 💡 用户名建议用英文，会显示在你所有的项目链接里，例如 `https://github.com/你的用户名`

### 2.2 补充资料：设置个人主页

注册完成后，建议立即设置 Profile：

1. 点击右上角头像 → **Settings** → **Profile**
2. 上传头像（一张真人照片或你喜欢的头像）
3. 写一段个人介绍（Bio）
4. （进阶）创建一个和用户名同名的仓库，README.md 会显示在个人主页上

这是一个好例子：`https://github.com/你的用户名/你的用户名`（创建一个特殊仓库）

### 2.3 安装 Git

Git 是 GitHub 的底层工具，需要先安装到电脑上。

**Windows**：下载 https://git-scm.com/download/win → 一路默认安装（安装时选"Git Bash"组件）

**macOS**：`brew install git`

**Linux**：`sudo apt install git` 或 `sudo yum install git`

安装后在终端（或 Git Bash）验证：

```bash
git --version
# 输出类似：git version 2.x.x
```

### 2.4 配置 Git（首次使用必须做）

打开终端（Windows 用 Git Bash），设置你的身份信息：

```bash
git config --global user.name "你的GitHub用户名"
git config --global user.email "你的GitHub邮箱"
```

查看配置是否成功：

```bash
git config --list
```

---

## 三、核心概念

| 概念 | 说明 |
|------|------|
| **Repository（仓库）** | 一个项目就是一个仓库，存放代码和文件的地方 |
| **Commit（提交）** | 拍一张代码"快照"，记录一次修改 |
| **Branch（分支）** | 独立的开发线，默认主分支叫 `main` |
| **Remote（远程）** | 远程仓库，即存放在 GitHub 上的仓库 |
| **Push（推送）** | 将本地代码上传到远程仓库 |
| **Pull（拉取）** | 将远程仓库的代码下载到本地 |
| **Pull Request（PR）** | 请求其他人把你的代码合并到他们的分支里 |
| **Issue（问题/任务）** | 提 Bug、提需求、讨论功能的地方 |
| **Fork（复刻）** | 复制别人的仓库到自己的账号下 |

---

## 四、GitHub 网页端操作（新手必学）

初学者不一定每次都需要用命令行，很多操作可以在网页上直接完成。

### 4.1 浏览项目

- 打开一个项目页面，可以看到代码文件列表
- 按 `.` 键可以直接在浏览器中打开 VS Code Web 版浏览代码
- 点击文件可以直接查看内容，点击 **History** 可以看修改历史

### 4.2 在网页上创建 Issue（提问题/提建议）

1. 进入项目仓库，点击上方的 **Issues** 标签
2. 点击绿色的 **New issue** 按钮
3. 填写标题和详细描述
4. 选择标签（Label），例如 `bug` / `enhancement` / `question`
5. 点击 **Submit new issue**

> 💡 一个优秀的 Issue 写法：描述清楚"发生了什么"、"期望什么"、"如何复现"

### 4.3 在网页上编辑文件

1. 进入仓库，点击要编辑的文件
2. 点击右上角的 ✏️ 图标
3. 在线编辑内容
4. 填写提交说明，点击 **Commit changes**
5. GitHub 会自动帮你创建一个分支并提交 PR 到原项目

### 4.4 如何 Star / Fork / Watch

- **Star**：项目页面右上角点 ⭐ 按钮，收藏该项目
- **Fork**：点击 **Fork** 按钮，复制一份到自己的账号
- **Watch**：点击 **Watch** 下拉菜单，选择 `All Activity` 关注所有动态

### 4.5 PR Review（代码审查）界面

> 如果你还不了解什么是 Pull Request（PR），建议先跳到[第八节](#八pull-requestprgithub-协作核心)阅读，再回来看这部分。

发起 PR 或别人给你提 PR 后，可以在 GitHub 网页上审查代码：

- **File Changed** 标签：逐行看改了什么代码
- **Comment**：在具体某行代码上留言
- **Approve**：审核通过，同意合并
- **Request Changes**：要求修改后才能合并
- **Merge pull request**：合并 PR

---

## 五、基本工作流程

### 5.1 创建第一个仓库

1. 登录 GitHub，点击右上角 `+` → **New repository**
2. 输入仓库名（如 `hello-world`）
3. 勾选 **Add a README file**
4. 点击 **Create repository**

### 5.2 克隆仓库到本地

```bash
git clone https://github.com/你的用户名/hello-world.git
cd hello-world
```

### 5.3 修改代码并提交

```bash
# 查看当前状态（推荐每次都先运行）
git status

# 添加文件到暂存区
git add 文件名          # 添加单个文件
git add .              # 添加所有文件

# 提交到本地仓库
git commit -m "提交说明"

# 推送到 GitHub
git push
```

**完整的流程示例：**

```bash
echo "欢迎来到我的第一个项目！" >> README.md
git add README.md
git commit -m "docs: 完善 README 说明"
git push
```

### 5.4 常用操作速查

```bash
# 拉取远程最新代码
git pull

# 查看提交历史
git log --oneline

# 查看改了哪些内容
git diff

# 回退到上一个版本
git reset --soft HEAD~1    # 保留修改，撤销 commit
git reset --hard HEAD~1    # 彻底丢弃修改（慎用！会丢失代码）
```

---

## 六、如何写好 Commit Message

写好 commit message 是参与开源项目的基本素养。推荐使用 **Conventional Commits 规范**：

```
<type>: <简短描述>

<可选的详细说明>
```

常见的 type 类型：

| 类型 | 含义 |
|------|------|
| `feat` | 新功能 |
| `fix` | 修复 Bug |
| `docs` | 文档更新 |
| `style` | 代码格式调整（不影响功能） |
| `refactor` | 代码重构 |
| `test` | 添加测试 |
| `chore` | 构建/工具相关 |

示例：

```bash
# 好的写法 - 简洁明了
git commit -m "fix: 修复登录按钮在移动端不可点击的问题"
git commit -m "feat: 新增用户头像上传功能"
git commit -m "docs: 更新安装说明"

# 不好的写法
git commit -m "修改了一些东西"
git commit -m "fix bug"
git commit -m "update"
```

---

## 七、分支管理

### 7.1 为什么要用分支？

分支让你可以在不影响主代码的情况下开发新功能或修复 Bug。

```
main  ──●────●────●─────────●──
           \          /
feature     ●──●──●──
```

### 7.2 分支操作

```bash
# 查看分支（当前分支前有 *）
git branch

# 创建新分支
git branch feature-login

# 切换到新分支
git checkout feature-login
# 或合并创建+切换（推荐）
git checkout -b feature-login

# 合并分支（先切回 main）
git checkout main
git merge feature-login

# 删除分支
git branch -d feature-login
```

### 7.3 实际场景演练

```bash
# 1. 从 main 创建新分支开发功能
git checkout -b add-header

# 2. 开发代码...
echo "<header>导航栏</header>" > index.html
git add .
git commit -m "feat: 添加导航栏"

# 3. 推送新分支到 GitHub
git push origin add-header

# 4. 合并到 main
git checkout main
git merge add-header
git push
```

---

## 八、Pull Request（PR）— GitHub 协作核心

PR 是 GitHub 最核心的协作方式。你开发完功能后，**请求项目维护者把你的代码合并到主分支**。

### 8.1 发起 PR 的步骤

1. 在 GitHub 上创建新分支并推送
2. 打开仓库页面，点击 **Compare & pull request**
3. 填写 PR 标题和说明
4. 点击 **Create pull request**
5. 等待仓库主人审核、合并

### 8.2 如何写好 PR 描述

一个优秀的 PR 描述能极大提高合并效率：

```markdown
## 做了什么
修复登录页面在 iOS Safari 上按钮错位的问题

## 原因
CSS flex 布局在 Safari 上有兼容性问题

## 测试方式
1. 在 iOS Safari 上打开登录页面
2. 确认按钮正常显示
3. 确认功能不受影响

Closes #123  (关联的 Issue 编号)
```

### 8.3 处理合并冲突

当两个人修改了同一个文件的同一部分时，会出现冲突。

```bash
# 拉取最新代码
git pull

# Git 会标记冲突位置，类似：
# <<<<<<< HEAD
# 你的代码
# =======
# 别人的代码
# >>>>>>> feature

# 手动编辑文件，保留想要的代码，删除标记符号
# 然后：
git add 文件名
git commit -m "fix: 解决合并冲突"
git push
```

---

## 九、与其他人协作

### 9.1 Fork + PR 工作流（参与开源项目）

这是参与任何开源项目的标准流程：

1. 在 GitHub 上找到感兴趣的项目，点击右上角 **Fork**
2. 克隆你 Fork 后的仓库：
   ```bash
   git clone https://github.com/你的用户名/项目名.git
   cd 项目名
   ```
3. 添加原项目仓库为**上游（upstream）**：
   ```bash
   git remote add upstream https://github.com/原作者/项目名.git
   ```
4. 创建分支开发：
   ```bash
   git checkout -b my-feature
   ```
5. 提交并推送：
   ```bash
   git push origin my-feature
   ```
6. 在 GitHub 上发起 PR 到原项目

### 9.2 如何同步上游仓库的更新（重要！）

Fork 之后原项目可能已经更新了，你需要同步上游代码才能继续开发：

```bash
# 1. 拉取上游仓库的最新代码
git fetch upstream

# 2. 切换到 main 分支
git checkout main

# 3. 把上游的 main 合并到你本地的 main
git merge upstream/main

# 4. 推送到你 GitHub 上的 Fork 仓库
git push origin main
```

或者用 rebase（更干净的提交历史）：

```bash
git fetch upstream
git checkout main
git rebase upstream/main
git push origin main
```

> 💡 养成好习惯：每次开新分支前先同步 upstream

### 9.3 团队协作

```bash
# 首次：克隆团队仓库
git clone https://github.com/团队名/项目名.git

# 每次开发前：拉取最新
git pull

# 创建功能分支
git checkout -b feature-xxx

# ...开发、提交、推送...
git push origin feature-xxx
```

---

## 十、如何参与开源项目（完整指南）

这是许多初学者最关心的部分，也是 GitHub 最有魅力的地方。

### 10.1 开源许可证简介

每个开源项目都有一个许可证，告诉你别人可以用代码做什么：

| 许可证 | 特点 |
|--------|------|
| **MIT** | 最宽松，任何人都可以随意使用、修改、商用 |
| **Apache 2.0** | 类似 MIT，额外包含专利保护条款 |
| **GPL** | 强制开源：用了我的代码，你的项目也必须开源 |
| **BSD** | 宽松，类似 MIT，强调保留版权声明 |

> 💡 创建自己的项目时，不知道选什么就选 **MIT**。GitHub 创建仓库时可以一键添加。

### 10.2 如何找到适合新手的开源项目

不要一上来就找大项目！按这个步骤来：

1. **在 GitHub 上搜索 `good first issue` 标签**：
   ```
   https://github.com/search?q=label%3Agood-first-issue&type=issues
   ```

2. **找 `help wanted` 标签**：表示维护者需要帮助

3. **推荐新手入门项目**：
   - [first-contributions](https://github.com/firstcontributions/first-contributions) — 专门为新手练 PR 流程的项目
   - [up-for-grabs](https://up-for-grabs.net) — 汇总了适合新手的项目
   - [Awesome for Beginners](https://github.com/MunGell/awesome-for-beginners) — 新手友好项目合集

4. **从文档和小修复开始**：修一个错别字、更新文档、修复一个注释——这些都是宝贵的第一次贡献！

### 10.3 参与前的准备工作

在动手之前，**一定要先看这些文档**：

- **README.md**：项目介绍、怎么安装、怎么用
- **CONTRIBUTING.md**：贡献指南，告诉你如何提交代码、代码风格要求
- **CODE_OF_CONDUCT.md**：行为准则，规定了社区交流的基本礼仪
- **LICENSE**：许可证文件

### 10.4 开源社区礼仪（重要！）

- **先搜索，再提问**：你的问题很可能已经有人问过了
- **不要在 Issue 里刷"+1"**：用 👍 emoji 表示支持就好
- **不要在 Issue 里直接 @ 维护者**：除非非常必要（如安全漏洞）
- **PR 尽量小**：一次只做一件事，方便维护者审查
- **保持耐心**：维护者也是志愿者，可能不会秒回
- **礼貌用语**：说"请"和"谢谢"，会让协作更愉快

---

## 十一、.gitignore 文件

有些文件不需要提交到 Git（如 `node_modules`、`.env` 密码文件、编译产物等）。创建 `.gitignore` 文件：

```gitignore
node_modules/
.env
.DS_Store
*.log
dist/
.vscode/
*.pyc
```

GitHub 提供了各种语言的模板：https://github.com/github/gitignore

---

## 十二、SSH 配置（免密码推送）

每次 push 输密码很麻烦，推荐用 SSH：

```bash
# 1. 生成 SSH 密钥
ssh-keygen -t ed25519 -C "你的邮箱"

# 2. 复制公钥
# Windows:
type %USERPROFILE%\.ssh\id_ed25519.pub
# macOS/Linux:
cat ~/.ssh/id_ed25519.pub

# 3. 添加到 GitHub
# Settings → SSH and GPG keys → New SSH key → 粘贴 → Add

# 4. 测试连接
ssh -T git@github.com
# 输出：Hi 用户名! You've successfully authenticated...

# 5. 克隆时用 SSH 地址
git clone git@github.com:用户名/仓库名.git
```

---

## 十三、GitHub Actions 简介（CI/CD）

GitHub Actions 是 GitHub 自带的自动化工具。当你推送代码时，它可以自动运行：

- 测试代码是否正常
- 检查代码格式
- 自动部署到服务器

> 💡 初学者可以先了解有这个东西，在项目里看到 `.github/workflows/` 文件夹时知道是干嘛的即可。

---

## 十四、常用技巧

### 14.1 撤销操作

```bash
# 撤销工作区的修改（还没 git add）
git restore 文件名

# 撤销暂存区（已经 git add）
git restore --staged 文件名

# 修改最近一次 commit 的说明
git commit --amend -m "新的说明"
```

### 14.2 查看谁改了什么

```bash
git blame 文件名
# 每行前面会显示作者、时间、提交号
```

### 14.3 暂存当前工作

```bash
# 临时保存修改（切换到其他分支时不丢失）
git stash
# 恢复
git stash pop
```

### 14.4 Tag（版本标签）

```bash
git tag v1.0.0
git push origin v1.0.0
```

---

## 十五、命令行 vs GitHub Desktop vs IDE

| 方式 | 适用人群 |
|------|----------|
| **命令行** | 推荐学习，理解原理，任何时候都能用 |
| **GitHub Desktop** | 图形界面，适合新手入门 https://desktop.github.com |
| **VS Code** | 内置 Git 面板，开发时最方便 |
| **Sourcetree** | 另一款优秀的 GUI 工具 |

**建议**：先用命令行学会核心概念，日常开发用 VS Code 或 GitHub Desktop 提高效率。

---

## 十六、常见问题

### Q: `fatal: not a git repository`
A: 当前目录不是 Git 仓库，先运行 `git init` 或 `git clone`

### Q: `Please tell me who you are`
A: 没有配置用户名/邮箱，运行：
```bash
git config --global user.name "你的名字"
git config --global user.email "你的邮箱"
```

### Q: `failed to push some refs`
A: 远程有比你新的代码，先 `git pull`

### Q: 推送时要求输入密码
A: 配置 SSH 或使用 Personal Access Token（推荐 SSH，参考 SSH 配置章节）

### Q: 我 Fork 的项目更新了，怎么办？
A: 参考 Fork 同步上游章节的命令，把 upstream 合并过来

### Q: 我不小心把敏感信息（密码/密钥）提交到 GitHub 了
A: 立即做三件事：
1. 在 GitHub 上删除或替换该文件
2. 刷新/更换该密钥（密码泄露了就是泄露了，删除 commit 也没用）
3. 把该文件加入 `.gitignore`

---

## 推荐学习路径

1. ☐ 读完本教程，跟着操作一遍
2. ☐ 在 [GitHub Learning Lab](https://lab.github.com) 做练习
3. ☐ 在 [first-contributions](https://github.com/firstcontributions/first-contributions) 项目上提一个 PR
4. ☐ 把自己的小项目放到 GitHub 上
5. ☐ 找一个项目修文档/修小 Bug（搜索 `good first issue`）
6. ☐ 学习更深入的知识：Git rebase、GitHub Actions、开源许可证选择

---

**记住：Git 是工具，多用就会了，犯错也没关系，Git 最擅长的就是后悔药。当你提交第一个 PR 被合并时，你会非常有成就感！**

---

> 本教程由 Claude Code 基于原版补充完善，增加了 GitHub 平台功能、开源项目参与指南、PR 规范、社区礼仪等内容。祝你在 GitHub 上玩得开心！
