<h2 align="left">Welcome to my GitHub profile!</h2>

###

<br clear="both">

<div align="left">
  <img src="https://github-readme-stats.vercel.app/api?username=fagundessana&hide_title=false&hide_rank=false&show_icons=true&include_all_commits=true&count_private=true&disable_animations=false&theme=midnight-purple&locale=en&hide_border=false" height="150" alt="stats graph"  />
  <img src="https://github-readme-stats.vercel.app/api/top-langs?username=fagundessana&locale=en&hide_title=false&layout=compact&card_width=320&langs_count=10&theme=midnight-purple&hide_border=false" height="150" alt="languages graph"  />
</div>

###

<br clear="both">

<p align="left">Currently studying:</p>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="30" alt="javascript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="30" alt="html5 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="30" alt="css3 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/java/java-original.svg" height="30" alt="java logo"  />
</div>

###

<p align="left">Conect with me:</p>

###

<img align="right" height="150" src="https://github.com/mari4souza/mari4souza/blob/main/src/study.gif?raw=true"  />

###

<div align="left">
  <a href="https://www.instagram.com/fagundessana/" target="_blank">
    <img src="https://img.shields.io/static/v1?message=Instagram&logo=instagram&label=&color=black&logoColor=purple&labelColor=&style=for-the-badge" height="35" alt="instagram logo"  />
  </a>
  <img src="https://img.shields.io/static/v1?message=Gmail&logo=gmail&label=&color=black&logoColor=purple&labelColor=&style=for-the-badge" height="35" alt="gmail logo"  />
</div>

###

<br clear="both">

<img src="https://raw.githubusercontent.com/fagundessana/fagundessana/output/snake.svg" alt="Snake animation" />

###

<div align="center">
  <img src="https://profile-counter.glitch.me/fagundessana/count.svg?"  />
</div>

### name: Generate snake animation

on:
  schedule: # execute every 12 hours
    - cron: "* */12 * * *"

  workflow_dispatch:

  push:
    branches:
    - main

jobs:
  generate:
    permissions:
      contents: write
    runs-on: ubuntu-latest
    timeout-minutes: 5
steps:
      - name: generate snake.svg
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: ${{ github.repository_owner }}
          outputs: dist/snake.svg?palette=github-dark


   - name: push snake.svg to the output branch
        uses: crazy-max/ghaction-github-pages@v3.1.0
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
