## Hi! Nice to see you! I'm Jaewon 👋

Welcome! I'm Jaewon, a Data Engineer from Seoul, South Korea, with a background in Mathematics and Computing Science.
I'm passionate about **real-time big data streaming**.

## Things I code with 
<img src="https://img.shields.io/badge/Python-3776AB?style=flat-square&logo=Python&logoColor=white"/>
<img src="https://img.shields.io/badge/Airflow-017CEE?style=flat-square&logo=Apache%20Airflow&logoColor=white"/>
<img src="https://img.shields.io/badge/Spark-E25A1C?style=flat-square&logo=Apache%20Spark&logoColor=white"/>
<img src="https://img.shields.io/badge/Hadoop-66CCFF?style=flat-square&logo=Apache%20Hadoop&logoColor=white"/>
<img src="https://img.shields.io/badge/Trino-DD00A1?style=flat-square&logo=Trino&logoColor=white"/>
<img src="https://img.shields.io/badge/Kafka-231F20?style=flat-square&logo=Apache%20Kafka&logoColor=white"/>
<img src="https://img.shields.io/badge/MySQL-4479A1?style=flat-square&logo=MySQL&logoColor=white"/>
<img src="https://img.shields.io/badge/Snowflake-29B5E8?style=flat-square&logo=Snowflake&logoColor=white"/>
<img src="https://img.shields.io/badge/Elasticsearch-005571?style=flat-square&logo=Elasticsearch&logoColor=white"/>
<img src="https://img.shields.io/badge/Postman-FF6C37?style=flat-square&logo=Postman&logoColor=white"/>


## GitHub Stats Card

[![Jaewon's GitHub stats](https://github-readme-stats.vercel.app/api?username=jaelim095)](https://github.com/jaelim095/github-readme-stats)
[![Top Langs](https://github-readme-stats.vercel.app/api/top-langs/?username=jaelim095)](https://github.com/anuraghazra/github-readme-stats)

## My latest posts
name: Update Blog Posts
on:
  push:
    branches: [ main ]
    paths-ignore:    # README.md 변경은 무시
      - 'README.md'
  pull_request:
    branches: [ main ]
  schedule:
    - cron: "0 */6 * * *"  # 6시간 마다 실행

jobs:
  update-readme:
    runs-on: ubuntu-latest
    
    steps:
    - uses: actions/checkout@v3
      with:
        token: ${{ secrets.GH_TOKEN }}
        
    - name: Set up Node.js
      uses: actions/setup-node@v3
      with:
        node-version: '18'
        cache: 'npm'
        
    - name: Install dependencies
      run: npm ci
        
    - name: Update README
      run: npm run update
        
    - name: Commit and push changes
      env:
        GH_TOKEN: ${{ secrets.GIT_TOKEN }}
      run: |
        git config --global user.name 'github-actions[bot]'
        git config --global user.email 'github-actions[bot]@users.noreply.github.com'
        git add README.md
        git diff --quiet && git diff --staged --quiet || git commit -m "docs: Update blog posts"

    - name: Push changes
      uses: ad-m/github-push-action@master
      with:
        github_token: ${{ secrets.GIT_TOKEN }}
        branch: main

## Connect with me 

<a href="https://instagram.com/limjaeon__" target="_blank">
  <img src="https://img.shields.io/badge/Instagram-E4405F?style=flat-square&logo=Instagram&logoColor=white"/>
</a>
<a href="https://linkedin.com/in/jaewon-lim-563510159/" target="_blank">
  <img src="https://img.shields.io/badge/LinkedIn-0A66C2?style=flat-square&logo=LinkedIn&logoColor=white"/>
</a>
<a href="https://velog.io/@jaelim095" target="_blank">
  <img src="https://img.shields.io/badge/Velog-20C997?style=flat-square&logo=Velog&logoColor=white"/>
</a>


