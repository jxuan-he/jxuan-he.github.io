# Jixuan He · 个人主页

极简学术主页：纯 HTML + CSS，无构建步骤，无外部依赖（字体已自托管在 `assets/fonts/`，
国内访问不依赖 Google Fonts），可直接托管在 GitHub Pages。

线上地址（部署后）：`https://jxuan-he.github.io`

## 目录结构

```
personal_page/
├── index.html                     # 页面内容（所有文字都在这里改）
├── style.css                      # 样式（蓝色主题，自动适配深色模式）
├── assets/
│   ├── profile.jpg                # 头像：把单人照改名成这个文件名放进来
│   └── profile-placeholder.svg    # 头像占位图（没有 profile.jpg 时自动显示）
├── .gitignore                     # 排除私人照片等文件
└── README.md
```

## 本地预览

```bash
cd D:/personal_page
python -m http.server 8000
# 浏览器打开 http://localhost:8000
```

直接双击 index.html 也能看，但起本地服务更接近真实部署效果。

## 更换头像

把裁剪好的单人照命名为 `profile.jpg`，放进 `assets/` 目录覆盖即可（jpg/png 均可，
若用 png 需把 index.html 里的 `profile.jpg` 改成对应文件名）。

## 部署到 GitHub Pages

1. 在 GitHub 上新建仓库，名字必须是 `jxuan-he.github.io`（用户名 + .github.io）。
2. 本目录初始化并推送：

   ```bash
   cd D:/personal_page
   git init
   git add .
   git commit -m "init: personal homepage"
   git branch -M main
   git remote add origin https://github.com/jxuan-he/jxuan-he.github.io.git
   git push -u origin main
   ```

3. 推送后 1–2 分钟访问 `https://jxuan-he.github.io` 即可看到页面
   （`username.github.io` 仓库默认从 main 分支发布，无需额外设置）。

> `.gitignore` 已排除 `me_and_my_girlfriend.jpg`，私人照片不会被推送到 GitHub，
> 请确认 `git status` 里看不到它再 push。

## 之后更新内容

- 改文字 / 加论文 / 加经历：编辑 `index.html`，每个区块都有清晰的 `<!-- section -->` 结构。
- 之后如果内容变多（论文列表、博客），可以考虑迁移到 Hugo/Astro 等静态生成器，现在不必。
