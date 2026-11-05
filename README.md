# 개인 포트폴리오 사이트

전북대학교 컴퓨터인공지능학부 학생의 관심 분야와 학습 및 프로젝트 경험을 소개하는 초급프로젝트 과제입니다.

- 활동명: eornjs4192
- 사이트: https://eornjs4192.github.io/MyWebPage/
- 저장소: https://github.com/eornjs4192/MyWebPage
- 배포 브랜치: main

## 사이트 구성

- 홈: 자기소개와 관심 분야, 현재 학습 내용
- 소개: AI 활용에 대한 관심과 학습 목표 및 실천 계획
- 활동 기록: Hugo 사이트 제작과 Vue 프로젝트 배포 실습
- 연락처: GitHub 계정과 포트폴리오 저장소 안내

## 주요 수정 위치

| 내용 | 파일 |
|---|---|
| 홈 | site/content/english/_index.md |
| 소개 | site/content/english/about/_index.md |
| 활동 기록 목록 | site/content/english/blog/_index.md |
| 활동 글 | site/content/english/blog/post-1.md |
| Vue 배포 실습 글 | site/content/english/blog/post-2.md |
| 연락처 내용 | site/content/english/contact/_index.md |
| 연락처 화면 구성 | site/layouts/contact.html |
| 404 오류 안내 화면 | site/layouts/404.html |
| 공통 문구 한국어 번역 | site/i18n/ko.yaml |
| 메뉴 | site/config/_default/menus.ko.toml |
| 로고와 사이트 설명 | site/config/_default/params.toml |
| 언어 설정 | site/config/_default/languages.toml |
| 사이트 제목 | site/hugo.toml |
| SNS 링크 | site/data/social.json |
| 이미지 | site/assets/images/ |

한국어 설정은 기존 content/english 폴더를 사용하도록 연결되어 있습니다.

Markdown은 원문을 볼 수 있는 모드에서 편집하고, 구분선과 들여쓰기를 유지합니다. 저장 후 git diff로 변경 내용을 확인합니다.

## 새 활동 글 추가 방법

1. site/content/english/blog 폴더에 중복되지 않는 이름의 .md 파일을 만듭니다.
2. 기존 활동 글의 맨 위 설정 구조를 참고하고 제목, 설명, 작성일, 분류와 태그를 수정합니다.
3. 작성자는 본인 활동명으로 지정하고, 공개할 글은 draft: false로 설정합니다.
4. 본문에 활동 목표, 수행 과정, 결과, 배운 점과 자료 출처를 작성합니다.
5. 이미지는 site/assets/images에 저장하고 기존 글과 같은 방식으로 경로를 연결합니다.
6. 커밋과 push 후 Actions 성공 여부 및 공개 목록과 본문을 확인합니다.

미래 날짜로 작성한 글은 기본 빌드에서 제외될 수 있으므로 작성일을 확인합니다. API 키나 비밀번호는 글과 이미지에 포함하지 않습니다.

## 빌드 환경과 방법

현재 GitHub Actions에 설정된 버전입니다.

- Python 3.12
- Node.js 24
- Go 1.27.1
- Hugo Extended 0.165.0
- Dart Sass 1.105.0

자동 배포에서는 저장소 최상위에서 다음 명령을 실행합니다.

```bash
python .github/pages_build.py --dependencies
python .github/pages_build.py --build
```

빌드 결과는 최상위 public 폴더에 생성됩니다. Windows 로컬에서 같은 명령을 실행하려면 필요한 도구가 설치되어 있어야 하며, 로컬 실행은 아직 검증하지 않았습니다.

## 배포 절차

1. 파일 수정 후 git diff로 변경 내용을 확인합니다.
2. 수정한 파일을 git add로 선택하고 커밋합니다.
3. main 브랜치에 push합니다.
4. GitHub Actions에서 해당 실행의 build와 deploy 성공 여부를 확인합니다.
5. 공개 사이트에서 내용과 링크를 직접 확인합니다.

배포 설정 파일은 .github/workflows/hugo-pages.yml입니다. 저장소의 Settings → Pages → Source는 GitHub Actions로 설정합니다.

## 출처와 직접 수행한 작업

- 테마: [Hugoplate](https://github.com/zeon-studio/hugoplate)
- 테마 제작자: [Zeon Studio](https://zeon.studio/)
- 초기 준비: 교수님이 제공한 prepare_github_pages.py 사용
- 직접 수정: 홈과 소개, 활동 글, 메뉴, 링크, 한국어 설정
- 직접 추가한 이미지: 사이트 홈 화면을 캡처한 portfolio-home.png

테마의 기존 코드와 이미지를 모두 직접 제작한 것은 아닙니다. 원본 라이선스와 제작자 출처는 유지합니다.

설정 수정과 오류 해결 과정에서 AI의 도움을 받았으며, 변경 내용을 확인하고 공개 사이트에서 동작을 점검했습니다.

---

## 원본 테마 안내

아래는 원본 Hugoplate README입니다. 원본 설치 방법은 현재 과제의 site 폴더와 교수님 제공 스크립트 방식과 다를 수 있습니다.

<h1 align="center">Hugo + Tailwind CSS Starter and Boilerplate</h1>

<p align="center">Hugoplate is a free starter template built with Hugo and Tailwind CSS v4.0, providing everything you need to jumpstart your Hugo project and save valuable time.</p>

<p align="center">Made with ♥ by <a href="https://zeon.studio/"> Zeon Studio</a></p>
<p align=center> If you find this project useful, please give it a ⭐ to show your support.</p>

<h2 align="center"> <a target="_blank" href="https://zeon.studio/preview?project=hugoplate" rel="nofollow">👀 Demo</a> | <a  target="_blank" href="https://pagespeed.web.dev/analysis/https-hugoplate-netlify-app/6lyxjw6t4r?form_factor=desktop">Page Speed (95+)🚀</a> |   <a target="_blank" href="https://app.sitepins.com/new/clone?name=Hugoplate&repository=https://github.com/zeon-studio/hugoplate?aff=hugoplate">
    <img src="https://sitepins.com/button.svg" alt="One Click Deploy With Sitepins">
  </a>
</h2>

<p align="center">
  <a href="https://github.com/gohugoio/hugo/releases/tag/v0.158.0" alt="Contributors">
    <img alt="hugo version" src="https://img.shields.io/static/v1?label=min-HUGO-version&message=0.158.0&color=f00&logo=hugo" />
  </a>

  <a href="https://github.com/zeon-studio/hugoplate/blob/main/LICENSE">
    <img src="https://img.shields.io/github/license/zeon-studio/hugoplate" alt="license">
  </a>

  <a href="https://github.com/zeon-studio/hugoplate">
    <img src="https://img.shields.io/github/languages/code-size/zeon-studio/hugoplate" alt="code size">
  </a>

  <a href="https://github.com/zeon-studio/hugoplate/graphs/contributors">
    <img src="https://img.shields.io/github/contributors/zeon-studio/hugoplate" alt="contributors">
  </a>
</p>

## Table of Contents

- [What's Included](#-whats-included)
  - [Key Features](#-key-features)
  - [15+ Pre-designed Pages](#-15-pre-designed-pages)
- [Tech Stack](#-tech-stack)
- [Getting Started](#-getting-started)
  - [Prerequisites](#-prerequisites)
  - [Project Setup](#-project-setup)
  - [Install Dependencies](#-install-dependencies)
  - [Development Command](#-development-command)
- [Customization](#-customization)
  - [Site Config](#-site-config)
  - [Site Params](#-site-params)
  - [Colors and Fonts](#-colors-and-fonts)
  - [Social Links](#-social-links)
- [Advanced Usage](#-advanced-usage)
- [Build And Deploy](#-build-and-deploy)
- [Guide to Staying Compliant](#-guide-to-staying-compliant)
- [Showcase](#-showcase)
- [Need Customization?](#-need-customization)

## 🎁 What's Included

We have included almost everything you need to start your Hugo project. Let's see what's included in this template:

### 📌 Key Features

- 👥 Multi-Authors
- 🎯 Similar Posts Suggestion
- 🔍 Search Functionality
- 🌑 Dark Mode
- 🏷️ Tags & Categories
- 🔗 Netlify setting pre-configured
- 📞 Support contact form
- 📱 Fully responsive
- 📝 Write and update content in Markdown
- 💬 Open-Remark Comment
- 🔳 Syntax Highlighting

### 📄 15+ Pre-designed Pages

- 🏠 Homepage
- 👤 About
- 📞 Contact
- 👥 Authors
- 👤 Author Single
- 📝 Blog
- 📝 Blog Single
- 🚫 Custom 404
- 💡 Elements
- 📄 Privacy Policy
- 🏷️ Tags
- 🏷️ Tag Single
- 🗂️ Categories
- 🗂️ Category Single
- 🔍 Search

### 📦 Tech Stack

- [Hugo](https://gohugo.io/)
- [Tailwind CSS v4.0](https://tailwindcss.com/)
- [AutoPrefixer](https://autoprefixer.github.io/)
- [Hugo Modules](https://gohugo.io/hugo-modules/) by [Gethugothemes](https://gethugothemes.com/hugo-modules)
- [Markdown](https://markdownguide.org/)
- [Prettier](https://prettier.io/)
- [Jshint](https://jshint.com/)
- [Netlify](https://www.netlify.com/)
- [Vercel](https://vercel.com/)
- [Github Actions](https://github.com/features/actions)
- [Gitlab Ci](https://docs.gitlab.com/ee/ci/)
- [AWS Amplify](https://aws.amazon.com/amplify/)

---

## 🚀 Getting Started

First you need to [clone](https://github.com/zeon-studio/hugoplate) or [download](https://github.com/zeon-studio/hugoplate/archive/refs/heads/main.zip) the template repository, and then let's get started with the following process:

### ⚙ Prerequisites

To start using this template, you need to have some prerequisites installed on your machine.

- [Hugo Extended v0.144+](https://gohugo.io/installation/)
- [Node v22+](https://nodejs.org/en/download/)
- [Go v1.24+](https://go.dev/doc/install)

### 👉 Project Setup

We built this custom script to make your project setup easier. It will create a new Hugo theme folder and clone the Hugoplate theme into it. Then move the exampleSite folder into the root directory. So that you can start your Hugo server without going into the exampleSite folder. Use the following command to setup your project.

```bash
npm run project-setup
```

### 👉 Install Dependencies

Install all the dependencies using the following command.

```bash
npm install
```

### 👉 Development Command

Start the development server using the following command.

```bash
npm run dev
```

### 🎬 Still Confused? Watch a Quick Video

https://github.com/zeon-studio/hugoplate/assets/58769763/c260c0ae-91be-42ce-b8db-aa7f11f777bd

---

## 📝 Customization

This template has been designed with a lot of customization options in mind. You can customize almost anything you want, including:

### 👉 Site Config

You can change the site title, base URL, language, theme, plugins, and more from the `hugo.toml` file.

### 👉 Site Params

You can customize all the parameters from the `config/_default/params.toml` file. This includes the logo, favicon, search, SEO metadata, and more.

### 👉 Colors and Fonts

You can change the colors and fonts from the `data/theme.json` file. This includes the primary color, secondary color, font family, and font size.

### 👉 Social Links

You can change the social links from the `data/social.json` file. Add your social links here, and they will automatically be displayed on the site.

---

## 🛠 Advanced Usage

We have added some custom scripts to make your life easier. You can use these scripts to help you with your development.

### 👉 Update Theme

If you want to update the theme, then you can use the following command. It will update the theme to the latest version.

```bash
npm run update-theme
```

> **Note:** This command will work after running the `project-setup` script.

### 👉 Update Modules

We have added a lot of modules to this template. You can update all the modules using the following command.

```bash
npm run update-modules
```

### 👉 Remove Dark Mode

If you want to remove dark mode from your project, you can use the following command to remove dark mode from your project.

```bash
npm run remove-darkmode
```

> **Note:** This command will work before running the `project-setup` script. If you have already run the `project-setup` command, then you have to run `npm run theme-setup` first, and then you can run this command. Afterward, you can run `npm run project-setup` again.

### 👉 Remove Multilingual

If you want to remove multilingual from your project, you can use the following command to remove multilingual from your project.

```bash
npm run remove-multilang
```

> **Note:** This command will work before running the `project-setup` script. If you have already run the `project-setup` command, then you have to run `npm run theme-setup` first, and then you can run this command. Afterward, you can run `npm run project-setup` again.

---

## 🚀 Build And Deploy

After you finish your development, you can build or deploy your project almost everywhere. Let's see the process:

### 👉 Build Command

To build your project locally, you can use the following command.

```bash
npm run build
```

### 👉 Deploy Site

We have provided 5 different deploy platform configurations with this template, so you can deploy easily.

- [Netlify](https://www.netlify.com/)
- [Vercel](https://vercel.com/)
- [Github Actions](https://github.com/features/actions)
- [Gitlab Ci](https://docs.gitlab.com/ee/ci/)
- [AWS Amplify](https://aws.amazon.com/amplify/)

And if you want to host some other hosting platforms. Then you can build your project, and you will get a `public` folder. that you can copy and paste on your hosting platform.

> **Note:** You must change the `baseURL` in the `hugo.toml` file. Otherwise, your site will not work properly.

---

<!-- edit with sitepins -->

## 📝 Edit Content with CMS

This template comes pre-configured with [**Sitepins**](https://sitepins.com?aff=hugoplate), a Git-based Headless CMS designed for seamless content management. You can update your website’s text, images, and configuration without touching a single line of code.

**How to get started:**

Click the Edit with Sitepins button below and follow the on-screen instructions to start editing your content visually.

  <a target="_blank" href="https://app.sitepins.com/new/clone?name=Hugoplate&repository=https://github.com/zeon-studio/hugoplate?aff=hugoplate">
    <img src="https://sitepins.com/button.svg" alt="Edit with Sitepins">
  </a>

## 🔒 Guide to Staying Compliant

### 🐞 Reporting Issues

We use GitHub Issues as the official bug tracker for this Template. Please search [existing issues](https://github.com/zeon-studio/hugoplate/issues). Someone may have already reported the same problem.
If your problem or idea has not been addressed yet, feel free to [open a new issue](https://github.com/zeon-studio/hugoplate/issues).

### 📝 License

Copyright (c) 2023 - Present, Designed & Developed by [Zeon Studio](https://zeon.studio/)

**Code License:** Released under the [MIT](https://github.com/zeon-studio/hugoplate/blob/main/LICENSE) license.

**Image license:** The images are only for demonstration purposes. They have their license, we don't have permission to share those images.

---

## 🌠 Showcase

List of some projects people are building with [**Hugoplate**!](https://github.com/zeon-studio/hugoplate/discussions/207)
Don't forget to add yours.

---

## 💻 Need Customization?

If you need a custom theme, theme customization, or complete website development services from scratch, you can [Hire Us](https://zeon.studio/estimate-project).
