# Qiang Wang Personal Website

This repository hosts the personal academic homepage of **Qiang Wang**. The site is built with **GitHub Pages** and **Jekyll**, and is used to present my profile, research interests, competition experience, projects, publications, and contact information.

Website:

```text
https://wangxqiang21.github.io/
```

## Overview

The homepage focuses on autonomous driving planning and control, including HD map route search, behavior decision-making, local trajectory planning, trajectory tracking control, simulation validation, and real-vehicle debugging.

Main sections:

- **Home**: personal profile, technical skills, and recent updates
- **Internship**: autonomous driving planning algorithm internship
- **Competition**: OnSite virtual-real fusion autonomous driving real-vehicle competition
- **Projects**: SPMT autonomous driving control algorithm development
- **Publications**: journal paper, patent, software copyright, and thesis information
- **English**: English version of the profile page

## File Structure

```text
.
├── index.md              # Chinese homepage
├── en.md                 # English homepage
├── internship.md         # Internship experience page
├── match.md              # Competition page
├── projects.md           # Projects page
├── publications.md       # Publications page
├── cn.md                 # Chinese page alias / backup page
├── _config.yml           # Jekyll site configuration and navigation
├── _includes/            # Shared HTML snippets
├── _layouts/             # Page layouts
├── assets/               # CSS, JavaScript, fonts
├── images/               # Avatar, favicon, project images
├── vedio/                # Project demonstration videos
└── file/                 # PDF and supporting files
```

The local preview dependencies are declared in `Gemfile`. The project uses Ruby 3.1+ and Jekyll 4.3.

## Local Preview

Install Ruby and Jekyll first. On Windows, RubyInstaller is recommended:

```text
https://rubyinstaller.org/downloads/
```

Then install the project dependencies:

```bash
bundle install
```

Run the site locally:

```bash
cd /home/wq/CV_page/wangxqiang21.github.io
bundle exec jekyll serve --livereload
```

Open:

```text
http://127.0.0.1:4000/
```

Useful local URLs:

```text
http://127.0.0.1:4000/internship/
http://127.0.0.1:4000/match/
http://127.0.0.1:4000/projects/
http://127.0.0.1:4000/publications/
http://127.0.0.1:4000/en/
```

## Updating Content

Most website content can be edited directly in Markdown files:

- `index.md`: Chinese homepage
- `en.md`: English homepage
- `match.md`: competition experience and videos
- `projects.md`: project experience
- `publications.md`: publications, patents, software copyright, and thesis
- `_config.yml`: site title, author profile, social links, and navigation bar

Static files should be placed in:

- `images/` for pictures and favicons
- `vedio/` for videos
- `file/` for PDF or other downloadable files

## Video Notes

Videos are embedded with HTML `<video>` tags. For better browser compatibility, MP4 videos should be encoded as **H.264 + AAC** and optimized with `faststart`.

Example FFmpeg commands:

```powershell
ffmpeg -y -i .\vedio\sim.mp4 -c:v libx264 -pix_fmt yuv420p -crf 28 -preset medium -movflags +faststart -c:a aac -b:a 128k .\vedio\sim_web.mp4

ffmpeg -y -i .\vedio\real.mp4 -c:v libx264 -pix_fmt yuv420p -crf 28 -preset medium -movflags +faststart -c:a aac -b:a 128k .\vedio\real_web.mp4
```

GitHub repositories do not accept individual files larger than 100 MB, so videos should be compressed before committing.

## Deployment

The site is deployed through GitHub Pages. After committing and pushing changes to the repository, GitHub Pages will automatically rebuild and publish the website.

Typical workflow:

```powershell
git status
git add .
git commit -m "Update personal homepage"
git push
```

## License

This website is adapted from an existing Jekyll personal website template. Please keep the original license information in `LICENSE` when reusing or modifying the template.
