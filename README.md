
<!-- Animated Header -->
<p align="center">
  <img src="https://capsule-render.vercel.app/api?type=waving&color=0:0F172A,50:2563EB,100:7C3AED&height=200&section=header&text=Nabil%20&fontSize=32&fontColor=FFFFFF&fontAlignY=38&desc=Informatics%20Student%20%7C%20Web%20Developer&descAlignY=58&descSize=16" width="100%" />
</p>

<!-- Typing Animation -->
<p align="center">
  <img src="https://readme-typing-svg.demolab.com/?font=Fira+Code&weight=500&size=20&pause=1000&color=38BDF8&center=true&vCenter=true&width=600&lines=Hi%2C+I'm+Nabil;Informatics+Student;Learning+Web+Development;Building+Projects+with+React+and+Laravel" alt="Typing SVG" />
</p>

<!-- Introduction -->
<h2 align="center">About Me</h2>

<p align="center">
  Informatics student interested in web development and UI/UX design.<br/>
  Currently learning to build responsive web applications<br/>
  and developing projects as part of my studies.
</p>

<!-- Tech Stack -->
<h2 align="center">Tech Stack</h2>

<p align="center">
  <img src="https://skillicons.dev/icons?i=html,css,js,react,vite,materialui,php,laravel,mysql,git,github,vscode&theme=dark" />
</p>

<!-- GitHub Statistics -->
<h2 align="center">GitHub Statistics</h2>

<p align="center">
  <img height="165" src="https://github-stats-extended.vercel.app/api?username=nabil&show_icons=true&theme=tokyonight&hide_border=true" alt="GitHub Stats" />
  <img height="165" src="https://github-stats-extended.vercel.app/api/top-langs/?username=nabil&layout=compact&theme=tokyonight&hide_border=true" alt="Top Languages" />
</p>

<!-- Contribution Streak -->
<p align="center">
  <img src="https://streak-stats.demolab.com?user=nabil&theme=tokyonight&hide_border=true" alt="GitHub Contribution Streak" />
</p>

<!-- Featured Project -->
<h2 align="center">Featured Project</h2>


<!-- Connect -->
<h2 align="center">Let's Connect</h2>

<p align="center">
  <a href="https://github.com/nabilibnualrasyid">
    <img src="https://img.shields.io/badge/GitHub-Profile-181717?style=for-the-badge&logo=github" />
  </a>
</p>

<p align="center">
  <i>Learning, building, and improving one project at a time.</i>
</p>


<p align="center">
  <img src="https://komarev.com/ghpvc/?username=nabilibnualrasyid&label=PROFILE+VIEWS&color=7C3AED&style=for-the-badge" alt="Profile views" />
</p>

<h2 align="center">🏆 GitHub Achievements</h2>

<p align="center">
  <img src="https://github-profile-trophy.vercel.app/?username=nabilibnualrasyid&theme=discord&no-frame=true&no-bg=true&row=1&column=6" width="100%" alt="GitHub trophies" />
</p>


name: Generate Snake Animation

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

permissions:
  contents: write

jobs:
  generate:
    runs-on: ubuntu-latest
    steps:
      - name: Generate contribution snake
        uses: Platane/snk/svg-only@v3
        with:
          github_user_name: nabilibnualrasyid
          outputs: |
            dist/github-snake.svg
            dist/github-snake-dark.svg?palette=github-dark

      - name: Publish snake animation
        uses: crazy-max/ghaction-github-pages@v4
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
