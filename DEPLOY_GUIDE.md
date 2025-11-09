# 🚀 DevFest Workshop 网站部署指南

## 步骤 1: 在 GitHub 上创建新仓库

1. 打开浏览器，访问：**https://github.com/new**

2. 填写仓库信息：
   - **Repository name**: `devfest-workshop-gallery`
   - **Description**: `Google DevFest Workshop - Chrome DevTools MCP Website`
   - **Visibility**: 选择 **Public** ✅
   - ⚠️ **重要**: 不要勾选以下选项：
     - ❌ Add a README file
     - ❌ Add .gitignore
     - ❌ Choose a license

3. 点击绿色的 **Create repository** 按钮

4. 创建成功后，GitHub 会显示一个页面，**先不要关闭这个页面**，我们稍后会用到仓库 URL

## 步骤 2: 推送代码到 GitHub

在终端中执行以下命令（**记得替换 YOUR_USERNAME 为你的 GitHub 用户名**）：

```bash
# 1. 进入项目目录
cd /Users/ximhan/work/ximhan/test/devtools-mcp-workshop-gallery

# 2. 初始化 Git 仓库（如果还没有）
git init

# 3. 添加所有文件
git add .

# 4. 创建提交
git commit -m "Initial commit: DevFest Workshop website"

# 5. 添加远程仓库（替换 YOUR_USERNAME）
git remote add origin https://github.com/YOUR_USERNAME/devfest-workshop-gallery.git

# 6. 重命名分支为 main
git branch -M main

# 7. 推送到 GitHub
git push -u origin main
```

### 如果遇到认证问题

如果推送时要求输入用户名和密码，可以使用 Personal Access Token：

```bash
# 使用 token 作为密码（替换 YOUR_TOKEN 和 YOUR_USERNAME）
git remote set-url origin https://YOUR_TOKEN@github.com/YOUR_USERNAME/devfest-workshop-gallery.git
git push -u origin main
```

## 步骤 3: 配置 GitHub Pages

1. 在 GitHub 仓库页面，点击顶部的 **Settings**（设置）标签

2. 在左侧菜单中，向下滚动找到 **Pages**，点击进入

3. 在 "Build and deployment" 部分：
   - **Source**: 选择 **Deploy from a branch**
   - **Branch**: 选择 **main**
   - **Folder**: 选择 **/ (root)**

4. 点击 **Save**（保存）按钮

5. 等待几秒钟，GitHub 会显示你的网站地址：
   ```
   https://YOUR_USERNAME.github.io/devfest-workshop-gallery/
   ```

## 步骤 4: 等待自动部署

1. 在仓库页面，点击 **Actions** 标签

2. 你会看到一个 "Deploy to GitHub Pages" 的工作流正在运行

3. 等待 1-2 分钟，直到看到绿色的 ✅ 标记

4. 部署完成后，访问你的网站 URL 查看效果

## 步骤 5: 验证网站

访问你的网站：`https://YOUR_USERNAME.github.io/devfest-workshop-gallery/`

检查以下内容：
- ✅ 首页正常显示
- ✅ 导航菜单可以点击
- ✅ GDG & DevFest 页面正常
- ✅ DevTools MCP 页面正常
- ✅ 关于我页面正常显示

## 快速命令总结

```bash
cd /Users/ximhan/work/ximhan/test/devtools-mcp-workshop-gallery
git init
git add .
git commit -m "Initial commit: DevFest Workshop website"
git remote add origin https://github.com/YOUR_USERNAME/devfest-workshop-gallery.git
git branch -M main
git push -u origin main
```

## 故障排除

### 问题 1: 推送被拒绝（rejected）

**解决方案**：
```bash
git pull origin main --allow-unrelated-histories
git push -u origin main
```

### 问题 2: GitHub Pages 显示 404

**解决方案**：
- 确保 `index.html` 文件在根目录
- 检查 GitHub Pages 设置中的 Source 是否正确
- 等待几分钟后刷新页面（部署需要时间）

### 问题 3: 部署工作流失败

**解决方案**：
- 在仓库的 **Actions** 标签中查看错误详情
- 确保 `.github/workflows/deploy.yml` 文件存在
- 检查文件格式是否正确

## 更新网站内容

如果需要更新网站内容：

```bash
# 1. 修改文件
# 2. 提交更改
git add .
git commit -m "Update website content"

# 3. 推送到 GitHub
git push origin main
```

GitHub Actions 会自动重新部署。

## 完成！🎉

你的网站现在已经部署到 GitHub Pages 了！

网站地址：`https://YOUR_USERNAME.github.io/devfest-workshop-gallery/`

