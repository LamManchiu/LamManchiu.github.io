# 个人简历网站实现计划

> **For agentic workers:** REQUIRED: Use superpowers:subagent-driven-development (if subagents available) or superpowers:executing-plans to implement this plan.

**Goal:** 创建一个简约专业的个人简历静态网站

**Architecture:** 单页滚动式设计，使用 HTML5 + CSS3 + 少量 JavaScript，无构建工具，直接部署到 GitHub Pages

**Tech Stack:** HTML5, CSS3, Vanilla JavaScript

---

## 文件结构

```
my-website/
├── index.html              # 主页面（所有内容）
├── css/
│   └── style.css           # 样式文件
├── js/
│   └── main.js            # 交互脚本
└── docs/
    └── superpowers/       # 文档
```

---

## 任务清单

### 任务 1: 创建目录结构

- [ ] 创建 `css/` 和 `js/` 目录

Run: `mkdir -p css js`

---

### 任务 2: 创建 index.html 主页面

**Files:**
- Create: `index.html`

- [ ] 创建包含所有区块的 HTML 文件

```html
<!DOCTYPE html>
<html lang="zh-CN">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>个人简历 - [姓名]</title>
    <link rel="stylesheet" href="css/style.css">
</head>
<body>
    <!-- 导航栏 -->
    <nav class="navbar">
        <div class="container nav-content">
            <a href="#hero" class="logo">[姓名]</a>
            <button class="hamburger" aria-label="菜单">
                <span></span>
                <span></span>
                <span></span>
            </button>
            <ul class="nav-links">
                <li><a href="#about">关于我</a></li>
                <li><a href="#experience">经历</a></li>
                <li><a href="#education">教育</a></li>
                <li><a href="#skills">技能</a></li>
                <li><a href="#projects">项目</a></li>
                <li><a href="#contact">联系</a></li>
            </ul>
        </div>
    </nav>

    <!-- Hero Section -->
    <section id="hero" class="hero">
        <div class="container">
            <h1>[姓名]</h1>
            <p class="subtitle">[职位/角色]</p>
            <a href="#contact" class="btn">联系我</a>
        </div>
    </section>

    <!-- About Section -->
    <section id="about" class="section">
        <div class="container">
            <h2 class="section-title">关于我</h2>
            <div class="about-content">
                <p>[个人简介内容]</p>
            </div>
        </div>
    </section>

    <!-- Experience Section -->
    <section id="experience" class="section bg-light">
        <div class="container">
            <h2 class="section-title">工作经历</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <h3>[公司名称]</h3>
                    <p class="timeline-date">[时间]</p>
                    <p>[职位]</p>
                    <ul>
                        <li>[主要成就/职责]</li>
                    </ul>
                </div>
            </div>
        </div>
    </section>

    <!-- Education Section -->
    <section id="education" class="section">
        <div class="container">
            <h2 class="section-title">教育背景</h2>
            <div class="timeline">
                <div class="timeline-item">
                    <h3>[学校名称]</h3>
                    <p class="timeline-date">[时间]</p>
                    <p>[专业] - [学位]</p>
                </div>
            </div>
        </div>
    </section>

    <!-- Skills Section -->
    <section id="skills" class="section bg-light">
        <div class="container">
            <h2 class="section-title">技能专长</h2>
            <div class="skills-grid">
                <div class="skill-category">
                    <h3>技术技能</h3>
                    <div class="skill-tags">
                        <span class="tag">[技能1]</span>
                        <span class="tag">[技能2]</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Projects Section -->
    <section id="projects" class="section">
        <div class="container">
            <h2 class="section-title">项目经验</h2>
            <div class="projects-grid">
                <div class="project-card">
                    <h3>[项目名称]</h3>
                    <p>[项目描述]</p>
                    <div class="tech-stack">
                        <span class="tag">[技术栈]</span>
                    </div>
                </div>
            </div>
        </div>
    </section>

    <!-- Contact Section -->
    <section id="contact" class="section bg-light">
        <div class="container">
            <h2 class="section-title">联系方式</h2>
            <div class="contact-links">
                <a href="mailto:[邮箱]" class="contact-item">📧 [邮箱]</a>
                <a href="https://github.com/[用户名]" class="contact-item">🐙 GitHub</a>
                <a href="https://linkedin.com/in/[用户名]" class="contact-item">💼 LinkedIn</a>
            </div>
        </div>
    </section>

    <!-- 页脚 -->
    <footer class="footer">
        <div class="container">
            <p>&copy; 2026 [姓名]. All rights reserved.</p>
        </div>
    </footer>

    <script src="js/main.js"></script>
</body>
</html>
```

---

### 任务 3: 创建 css/style.css 样式文件

**Files:**
- Create: `css/style.css`

- [ ] 创建完整样式文件

```css
/* CSS Variables */
:root {
    --primary-color: #2c3e50;
    --secondary-color: #ecf0f1;
    --accent-color: #3498db;
    --text-color: #333;
    --text-light: #666;
    --white: #fff;
    --transition: all 0.3s ease;
}

/* Reset */
* {
    margin: 0;
    padding: 0;
    box-sizing: border-box;
}

/* Base */
html {
    scroll-behavior: smooth;
}

body {
    font-family: -apple-system, BlinkMacSystemFont, "Segoe UI", Roboto, sans-serif;
    line-height: 1.6;
    color: var(--text-color);
}

/* Container */
.container {
    max-width: 1100px;
    margin: 0 auto;
    padding: 0 20px;
}

/* Navbar */
.navbar {
    position: fixed;
    top: 0;
    left: 0;
    right: 0;
    background: var(--white);
    box-shadow: 0 2px 10px rgba(0,0,0,0.1);
    z-index: 1000;
}

.nav-content {
    display: flex;
    justify-content: space-between;
    align-items: center;
    padding: 15px 20px;
}

.logo {
    font-size: 1.5rem;
    font-weight: bold;
    color: var(--primary-color);
    text-decoration: none;
}

.nav-links {
    display: flex;
    list-style: none;
    gap: 30px;
}

.nav-links a {
    color: var(--text-color);
    text-decoration: none;
    transition: var(--transition);
}

.nav-links a:hover {
    color: var(--accent-color);
}

/* Hero */
.hero {
    height: 100vh;
    display: flex;
    align-items: center;
    justify-content: center;
    text-align: center;
    background: linear-gradient(135deg, var(--primary-color), var(--accent-color));
    color: var(--white);
}

.hero h1 {
    font-size: 3.5rem;
    margin-bottom: 10px;
}

.hero .subtitle {
    font-size: 1.5rem;
    margin-bottom: 30px;
    opacity: 0.9;
}

.btn {
    display: inline-block;
    padding: 12px 30px;
    background: var(--white);
    color: var(--primary-color);
    text-decoration: none;
    border-radius: 5px;
    font-weight: bold;
    transition: var(--transition);
}

.btn:hover {
    transform: translateY(-2px);
    box-shadow: 0 5px 20px rgba(0,0,0,0.2);
}

/* Sections */
.section {
    padding: 80px 0;
}

.bg-light {
    background: var(--secondary-color);
}

.section-title {
    font-size: 2.5rem;
    color: var(--primary-color);
    text-align: center;
    margin-bottom: 50px;
}

/* Timeline */
.timeline {
    max-width: 800px;
    margin: 0 auto;
}

.timeline-item {
    padding: 20px;
    background: var(--white);
    border-radius: 8px;
    margin-bottom: 20px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
}

.timeline-item h3 {
    color: var(--primary-color);
    margin-bottom: 5px;
}

.timeline-date {
    color: var(--accent-color);
    font-size: 0.9rem;
    margin-bottom: 10px;
}

.timeline-item ul {
    margin-top: 10px;
    padding-left: 20px;
}

/* Skills */
.skills-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(250px, 1fr));
    gap: 30px;
    max-width: 800px;
    margin: 0 auto;
}

.skill-category {
    text-align: center;
}

.skill-category h3 {
    margin-bottom: 15px;
    color: var(--primary-color);
}

.skill-tags {
    display: flex;
    flex-wrap: wrap;
    gap: 10px;
    justify-content: center;
}

.tag {
    background: var(--accent-color);
    color: var(--white);
    padding: 5px 15px;
    border-radius: 20px;
    font-size: 0.9rem;
}

/* Projects */
.projects-grid {
    display: grid;
    grid-template-columns: repeat(auto-fit, minmax(300px, 1fr));
    gap: 30px;
    max-width: 1000px;
    margin: 0 auto;
}

.project-card {
    background: var(--white);
    padding: 30px;
    border-radius: 8px;
    box-shadow: 0 2px 10px rgba(0,0,0,0.05);
    transition: var(--transition);
}

.project-card:hover {
    transform: translateY(-5px);
    box-shadow: 0 5px 20px rgba(0,0,0,0.1);
}

.project-card h3 {
    color: var(--primary-color);
    margin-bottom: 10px;
}

.project-card p {
    color: var(--text-light);
    margin-bottom: 15px;
}

.tech-stack {
    display: flex;
    flex-wrap: wrap;
    gap: 8px;
}

/* Contact */
.contact-links {
    display: flex;
    flex-direction: column;
    align-items: center;
    gap: 20px;
}

.contact-item {
    display: flex;
    align-items: center;
    gap: 10px;
    color: var(--text-color);
    text-decoration: none;
    font-size: 1.2rem;
    transition: var(--transition);
}

.contact-item:hover {
    color: var(--accent-color);
}

/* Footer */
.footer {
    background: var(--primary-color);
    color: var(--white);
    text-align: center;
    padding: 20px 0;
}

/* Mobile Responsive */
@media (max-width: 768px) {
    .hamburger {
        display: flex;
        flex-direction: column;
        justify-content: space-between;
        width: 30px;
        height: 24px;
        background: none;
        border: none;
        cursor: pointer;
        padding: 0;
    }

    .hamburger span {
        display: block;
        width: 100%;
        height: 3px;
        background: var(--primary-color);
        border-radius: 2px;
        transition: var(--transition);
    }

    .hamburger.active span:nth-child(1) {
        transform: rotate(45deg) translate(6px, 6px);
    }

    .hamburger.active span:nth-child(2) {
        opacity: 0;
    }

    .hamburger.active span:nth-child(3) {
        transform: rotate(-45deg) translate(6px, -6px);
    }

    .nav-links {
        display: none;
        position: absolute;
        top: 100%;
        left: 0;
        right: 0;
        background: var(--white);
        flex-direction: column;
        padding: 20px;
        gap: 15px;
        box-shadow: 0 5px 20px rgba(0,0,0,0.1);
    }

    .nav-links.active {
        display: flex;
    }

    .hero h1 {
        font-size: 2.5rem;
    }

    .hero .subtitle {
        font-size: 1.2rem;
    }

    .section-title {
        font-size: 2rem;
    }
}
```

---

### 任务 4: 创建 js/main.js 交互脚本

**Files:**
- Create: `js/main.js`

- [ ] 创建 JavaScript 文件

```javascript
// 导航栏交互和汉堡菜单
document.addEventListener('DOMContentLoaded', function() {
    const hamburger = document.querySelector('.hamburger');
    const navLinks = document.querySelector('.nav-links');

    // 汉堡菜单切换
    hamburger.addEventListener('click', function() {
        navLinks.classList.toggle('active');
        hamburger.classList.toggle('active');
    });

    // 点击导航链接后关闭菜单
    const navLinksItems = document.querySelectorAll('.nav-links a');
    navLinksItems.forEach(link => {
        link.addEventListener('click', function() {
            navLinks.classList.remove('active');
            hamburger.classList.remove('active');
        });
    });

    // 桌面端平滑滚动（移动端通过点击事件已处理）
    const isDesktop = window.matchMedia('(min-width: 769px)').matches;
    if (isDesktop) {
        document.querySelectorAll('a[href^="#"]').forEach(anchor => {
            anchor.addEventListener('click', function(e) {
                e.preventDefault();
                const targetId = this.getAttribute('href');
                const targetSection = document.querySelector(targetId);
                if (targetSection) {
                    targetSection.scrollIntoView({
                        behavior: 'smooth',
                        block: 'start'
                    });
                }
            });
        });
    }
});
```

---

### 任务 5: 本地测试

- [ ] 使用浏览器打开 `index.html` 验证页面显示

Run: 直接在浏览器中打开 index.html 文件

---

### 任务 6: 提交代码

- [ ] 添加所有文件到 git 并提交

Run:
```bash
git add index.html css/style.css js/main.js
git commit -m "feat: add personal website with all sections

- Hero section with name and title
- About section
- Experience timeline
- Education timeline
- Skills tags
- Projects grid
- Contact section
- Responsive design for mobile

Co-Authored-By: Claude Sonnet 4.6 <noreply@anthropic.com>"
```

---

### 任务 7: 推送到 GitHub

- [ ] 推送到远程仓库

Run:
```bash
git push origin main
```

---

### 任务 8: 配置 GitHub Pages

**手动步骤（需要用户在 GitHub 上操作）：**
1. 访问 https://github.com/Stars-Chan/my-website
2. 进入 Settings > Pages
3. Source 选择 "Deploy from a branch"
4. Branch 选择 "main" 和 "/ (root)"
5. 点击 Save
6. 等待几分钟后访问 https://stars-chan.github.io/my-website

---

## 后续个性化步骤

网站创建后，用户需要编辑 `index.html` 替换以下占位符：
- `[姓名]` → 真实姓名
- `[职位/角色]` → 职位描述
- `[个人简介内容]` → 个人简介
- `[公司名称]`、[时间]、[职位] 等 → 真实工作经历
- `[学校名称]`、[专业]、[学位] → 真实教育背景
- `[技能1]`、[技能2] 等 → 真实技能
- `[项目名称]`、[项目描述] 等 → 真实项目经验
- `[邮箱]`、[GitHub用户名]、[LinkedIn用户名] → 真实联系方式
