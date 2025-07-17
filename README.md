<h1 align="left">🌐 Olá, eu sou o Ryan</h1>

###

<p align="left">🚀 Iniciando minha trajetória na tecnologia<br><br>Assim como tantas pessoas inspiradoras na área, estou oficialmente dando meus primeiros passos no universo de Análise e Desenvolvimento de Sistemas.<br><br>🎓 Atualmente estudando e mergulhando em linguagens como HTML, CSS, JavaScript e explorando frameworks como Node.js e React, estou determinado a construir soluções que unem design, lógica e propósito.<br><br>🔍 Com olhar analítico e espírito curioso, minha meta é transformar problemas em projetos e ideias em código.<br><br>📚 Sempre aberto a dicas, boas conversas e conexões com quem também vive esse mundo de desenvolvimento.</p>

###

<h2 align="left"></h2>

###

<p align="left">✨ Técnico em Desenvolvimento de Sitemas pela UNINOVE<br><br>📚 Cursando Análise e Desenvolvimento de Sistemas. <br><br>🌍 Explorando novas tecnologias e desenvolvendo soluções de software.</p>

###

<h2 align="left"></h2>

###

<br clear="both">

<picture>
  <source media="(prefers-color-scheme: dark)" srcset="https://raw.githubusercontent.com/RyanMS27/RyanMS27/output/pacman-contribution-graph-dark.svg">
  <source media="(prefers-color-scheme: light)" srcset="https://raw.githubusercontent.com/RyanMS27/RyanMS27/output/pacman-contribution-graph.svg">
  <img alt="pacman contribution graph" src="https://raw.githubusercontent.com/RyanMS27/RyanMS27/output/pacman-contribution-graph.svg">
</picture>

###

<h2 align="left"></h2>

###

<div align="left">
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/javascript/javascript-original.svg" height="40" alt="javascript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/typescript/typescript-original.svg" height="40" alt="typescript logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/react/react-original.svg" height="40" alt="react logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nodejs/nodejs-original.svg" height="40" alt="nodejs logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/nestjs/nestjs-original.svg" height="40" alt="nestjs logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/html5/html5-original.svg" height="40" alt="html5 logo"  />
  <img width="12" />
  <img src="https://cdn.jsdelivr.net/gh/devicons/devicon/icons/css3/css3-original.svg" height="40" alt="css3 logo"  />
</div>

name: Generate snake animation

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
###
