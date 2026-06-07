# 博客设置指南

## 快速开始

这个博客系统使用 GitHub Issues 来存储和发布文章，并提供 Mac 风格的简洁界面。

## 功能特性

✨ **Mac 风格设计** - 简洁、优雅、原生感  
📝 **GitHub Issues 驱动** - 文章存储在 Issues 中  
🔐 **用户认证** - 支持 GitHub 登陆发布文章  
📱 **响应式设计** - 完美适配各种设备  
⚡ **快速加载** - 缓存机制提高性能  
🎨 **Markdown 支持** - 完整的 Markdown 渲染  

## 设置步骤

### 1. 获取 GitHub Personal Access Token

1. 访问 https://github.com/settings/tokens
2. 点击 "Generate new token (classic)"
3. 设置以下权限：
   - `repo` - 完全控制私有仓库
   - `public_repo` - 访问公开仓库
4. 点击 "Generate token" 并保存（只会显示一次）

### 2. 首次发布文章

1. 打开博客网站：https://Abdi-6666666.github.io
2. 点击 "GitHub 登陆" 按钮
3. 粘贴你的 Personal Access Token
4. 成功登陆后，"✏️ 发布文章" 按钮会出现
5. 点击发布文章，填写标题、内容和标签
6. 提交后文章会自动显示在博客上

### 3. 文章管理

#### 添加标签

在发布文章时，可以添加多个标签（用逗号分隔）。这些标签会显示在文章卡片上。

```
标签示例: 技术, JavaScript, 分享
```

#### 文章格式

支持标准 Markdown 格式：

```markdown
# 标题一级
## 标题二级
### 标题三级

**加粗文本** 和 *斜体文本*

`行内代码`

```python
代码块示例
```

[链接文本](url)

> 引用文本
```

#### 编辑已发布的文章

1. 访问 GitHub Issues 页面
2. 找到对应的文章 Issue
3. 编辑内容或标签
4. 博客会自动刷新（可能需要 5 分钟更新缓存）

#### 删除文章

1. 在 GitHub Issues 页面找到文章
2. 关闭（Close）或删除（Delete）该 Issue
3. 博客会自动更新

### 4. 自定义设置

编辑 `styles.css` 中的 CSS 变量来自定义外观：

```css
:root {
    --primary-bg: #ffffff;
    --accent-color: #0071e3;
    /* ... 其他变量 */
}
```

## 文章发布工作流程

```
1. 在博客界面填写文章信息
   ↓
2. 点击"发布"按钮
   ↓
3. 系统使用你的 Token 在 GitHub 创建 Issue
   ↓
4. Issue 被标记为 "blog-post" 标签
   ↓
5. 博客读取该 Issue 并显示在首页
   ↓
6. 用户可以点击查看全文
```

## 技术架构

### 前端技术
- HTML5
- CSS3（带 CSS Variables）
- Vanilla JavaScript（无框架）
- GitHub REST API

### 存储方式
- 文章内容：GitHub Issues
- 缓存：LocalStorage（5分钟过期）
- 认证信息：LocalStorage

### 安全性
- Personal Access Token 存储在浏览器 LocalStorage
- 建议定期更新 Token
- 不要在公开场合分享 Token

## 常见问题

### Q: Token 安全吗？
**A:** Token 存储在你的浏览器 LocalStorage 中。为了安全起见：
- 定期更新 Token（GitHub 设置中可管理）
- 不要在其他设备登陆
- 清除浏览器数据时会删除 Token

### Q: 文章为什么没有显示？
**A:** 请检查以下几点：
1. Issue 是否有 "blog-post" 标签
2. 浏览器缓存是否过期（5分钟）
3. GitHub API 是否可访问
4. Token 是否仍然有效

### Q: 如何重置 Token？
**A:** 
1. 访问 https://github.com/settings/tokens
2. 找到对应的 Token 点击 "Delete"
3. 创建新的 Token
4. 在博客重新登陆使用新 Token

### Q: 支持多用户吗？
**A:** 是的！每个用户用自己的 Token 登陆，可以发布自己的文章。所有文章会显示作者信息。

### Q: 我想要更高级的功能？
**A:** 可以考虑升级为：
- 评论系统（使用 GitHub Discussions）
- 分类功能
- 搜索功能
- 社交分享

## 部署到 GitHub Pages

这个博客已经配置为在 GitHub Pages 上运行：

1. 仓库名称必须是 `{username}.github.io`
2. 主分支（main）的内容会自动部署
3. 访问地址：`https://{username}.github.io`

## 文件结构

```
.
├── index.html          # 主页面
├── styles.css          # 样式表（Mac 风格）
├── script.js           # 主逻辑脚本
├── SETUP.md            # 本文件
└── README.md           # 项目说明
```

## 许可证

MIT License - 可自由使用和修改

## 联系方式

有问题？可以通过以下方式联系：
- GitHub Issues：https://github.com/Abdi-6666666/Abdi-6666666.github.io/issues
- Email：见 GitHub 个人资料

---

祝你使用愉快！✨
