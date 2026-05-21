# 个人主页修改指南

这份说明是给后续维护用的：哪些地方改个人信息，哪些页面现在隐藏了，以及不用的内容以后怎么安全删除。

## 1. 最常改的文件

- `_config.yml`：网站标题、简介、邮箱、头像、社交链接、顶部导航。
- `index.md`：中文首页，也是访问网站时默认打开的页面。
- `cn.md`：中文页的保留入口，对应 `/cn/`。
- `en.md`：英文简介页，对应 `/en/`。
- `publications.md`：论文页，对应 `/publications/`。
- `projects.md`：项目页，对应 `/projects/`。
- `images/`：头像、校徽、项目图片等静态图片。
- `file/`：简历 PDF、论文 PDF、其他下载文件。

## 2. 修改个人信息

打开 `_config.yml`，重点改这些字段：

```yml
title: Qiang Wang
description: 王强的个人主页，包含个人简介、论文、项目与联系方式。

owner:
  name: Qiang Wang
  avatar: whut_log.png
  email: wangxqiang21@163.com
  github: wangxqiang21
  scholar:
  researchgate:
  zhihu:
  xiaohongshu:
  bilibili:
```

头像文件放到 `images/` 目录里，然后把 `owner.avatar` 改成文件名，例如：

```yml
avatar: my-photo.jpg
```

如果某个社交账号不想显示，直接把那一行注释掉或留空。

## 3. 修改顶部导航

导航在 `_config.yml` 的 `links` 里：

```yml
links:
  - title: 首页
    url: /
  - title: 论文
    url: /publications/
  - title: 项目
    url: /projects/
  - title: English
    url: /en/
```

想恢复“获奖、服务、博客、兴趣”等入口，只要把对应页面加回这里即可，例如：

```yml
  - title: 获奖
    url: /awards/
  - title: 博客
    url: /blogs/
```

## 4. 现在保留但不显示的内容

这些文件还在，只是没有放到顶部导航里：

- `services.md`
- `awards.md`
- `hobbies.md`
- `blogs.md`
- `blogs/`
- `file/awards-zh.md`
- `file/publications-zh.md`

也就是说它们没有被删，以后需要时可以重新加入导航，或复制里面的格式。

`backup/` 目录也保留了，但已经在 `_config.yml` 的 `exclude` 里排除，不会参与网站构建。这样可以避免旧备份页面和新页面争抢同一个网址，比如 `/projects/` 或 `/publications/`。

## 5. 论文页怎么填

编辑 `publications.md`，按这个格式添加：

```md
- [论文标题](论文链接)<br>
  **Qiang Wang**, Author B, Author C<br>
  会议或期刊名称，年份。<br>
```

如果暂时没有某类成果，可以保留“待补充”，也可以删除对应小节。

## 6. 项目页怎么填

编辑 `projects.md`，按这个格式添加：

```md
### [项目名称](项目链接)

一句话说明项目目标、你的角色，以及使用到的技术或方法。

- 时间：2025.01 - 2025.06
- 角色：负责人 / 主要成员 / 独立完成
- 关键词：通信、AI、系统实现
```

如果有项目截图，把图片放到 `images/`，然后在项目条目里引用：

```md
<img src="/images/project-demo.png">
```

## 7. 不用的东西怎么删

建议按这个顺序来，比较不容易误删：

1. 先从 `_config.yml` 的 `links` 里移除导航入口。
2. 本地预览或推到 GitHub Pages 后确认页面不再需要。
3. 删除对应的 `.md` 文件和只被它使用的图片/PDF。
4. 如果删除了整组内容，比如博客，再删除 `blogs/` 目录。
5. 删除后搜索一下旧链接，例如搜索 `blogs/`、`awards/`，确认没有页面还引用它们。

常见对应关系：

- 不要博客：删 `blogs.md` 和 `blogs/`。
- 不要获奖页：删 `awards.md`，以及不需要的 `file/awards-zh.md`。
- 不要服务页：删 `services.md`。
- 不要兴趣页：删 `hobbies.md`。
- 不要中文旧文件页：删 `file/publications-zh.md`、`file/awards-zh.md`。
- 不要旧模板备份：删 `backup/`。

## 8. 域名和统计

原站点的 `CNAME` 已经移到 `backup/CNAME-original.txt`，根目录不再保留 active `CNAME`，因此默认会使用 GitHub Pages 地址 `https://wangxqiang21.github.io`。如果你以后有自己的域名，在根目录新建 `CNAME`，内容只写你的域名，例如：

```txt
www.example.com
```

访问统计已经改成可选配置。需要启用时，在 `_config.yml` 里填写：

```yml
google_analytics: "G-你的ID"
counter_dev_id: "你的counter.dev ID"
```

不填写就不会加载统计脚本。
