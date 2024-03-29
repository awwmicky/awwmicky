```yml
name: Generate DevCard - Daily.dev Stats Data

on:
  # auto run from Actions Tab
  workflow_dispatch:
  push:
    branches:
    - main
    - develop
  schedule:
  - cron: "0 0 * * *"

jobs:
  DevCard:
    name: Generate DevCard 🎴
    runs-on: ubuntu-latest
    steps:
      # repo under $GITHUB_WORKSHOP
      - uses: actions/checkout@master
      # generate devcard svg
      - uses: dailydotdev/action-devcard@2.0.5
        id: devcard-svg
        with:
          devcard_id: ${{ secrets.DEVCARD_ID }}
          commit_branch: output
          commit_filename: dist/devcard.svg
      # status: test/debug
      - run: git status
      # push the changes
      - name: Push changes
        uses: ad-m/github-push-action@master
        with:
          github_token: ${{ secrets.GITHUB_TOKEN }}
          branch: main
          force: true
      # target branch 'output'
      - uses: crazy-max/ghaction-github-pages@v2
        with:
          target_branch: output
          build_dir: dist
        env:
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}