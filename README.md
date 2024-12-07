# Hi there🙋‍♂️it's me Dinesh 
### I extend a warm welcome to my GitHub profile❗ I'm a passionate developer interested in building cool projects. Here's a little bit about me
*Computer Science Engineering Student*
  - 📋Here's My <a href ="name">Portfolio</a>
 - 🛠️ Currently working on **Algorithm Visualizer** – a project is focused on creating an interactive and graphical Algorithm Visualizer, showcasing step-by-step executions of algorithms like sorting, searching, and graph traversal
 

name: GitHub Stats

on:
  schedule:
    - cron: "0 0 * * *"
  workflow_dispatch:

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
    - name: Checkout Repository
      uses: actions/checkout@v2

    - name: Generate GitHub Stats
      run: |
        curl -s https://github-readme-stats.vercel.app/api?username=YOUR_GITHUB_USERNAME&show_icons=true&theme=dark > stats.svg
        curl -s https://github-readme-stats.vercel.app/api/top-langs/?username=YOUR_GITHUB_USERNAME&layout=compact&theme=dark > top-langs.svg

    - name: Upload Stats to GitHub
      uses: actions/upload-artifact@v2
      with:
        name: stats
        path: |
          stats.svg
          top-langs.svg

