---
title: Setup for Chirpy Jekyll Page Deployment workflow
author: jaeman
date: 2025-02-10 05:02:00 +0900
categories: [Github Blog]
tags: [Chirpy, Jekyll, Github Page, Github Actions, workflows]
toc: true
---

## Prerequisition
- Github Page setup
- Chripy basic setup

I believe you have seen the tutorials of many guides about Chripy and Github page setup from many other websites.  
This post is only aimed configuration of **Chirpy** auto deployment flow.

## Default Action Workflow Provided by Github
As you click the [Actions] -> [New workflow] in your Github Page repository,  
<img width="859" alt="Screenshot24 25 12" src="https://github.com/user-attachments/assets/3e31bf46-a441-4029-bc22-ea85d9d178e8" />
  
  
You can search ```jekyll``` for the default Jekyll Deployment Workflow Provided by Github.  
<img width="1127" alt="Screenshot14 21 13" src="https://github.com/user-attachments/assets/70c37710-76a3-406d-9b31-8f453102a9d0" />
  
And it whould gives you a `.yml` workflow file as below

<details markdown="1">
<summary><strong>jekyll-gh-pages.yml</strong></summary>

```yaml
# Sample workflow for building and deploying a Jekyll site to GitHub Pages
name: Deploy Jekyll with GitHub Pages dependencies preinstalled

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ["master"]

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets permissions of the GITHUB_TOKEN to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow only one concurrent deployment, skipping runs queued between the run in-progress and latest queued.
# However, do NOT cancel in-progress runs as we want to allow these production deployments to complete.
concurrency:
  group: "pages"
  cancel-in-progress: false

jobs:
  # Build job
  build:
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Build with Jekyll
        uses: actions/jekyll-build-pages@v1
        with:
          source: ./
          destination: ./_site
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3

  # Deployment job
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```
</details>
  
  
But it does not work properly on Chirpy  
Replace it to
<details markdown="1">
<summary><strong>pages-deploy.yml</strong></summary>

```yaml
name: "Build and Deploy"
on:
  push:
    branches:
      - main
      - master
    paths-ignore:
      - .gitignore
      - README.md
      - LICENSE

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

permissions:
  contents: read
  pages: write
  id-token: write

# Allow one concurrent deployment
concurrency:
  group: "pages"
  cancel-in-progress: true

jobs:
  build:
    runs-on: ubuntu-latest

    steps:
      - name: Checkout
        uses: actions/checkout@v4
        with:
          fetch-depth: 0
          # submodules: true
          # If using the 'assets' git submodule from Chirpy Starter, uncomment above
          # (See: https://github.com/cotes2020/chirpy-starter/tree/main/assets)

      - name: Setup Pages
        id: pages
        uses: actions/configure-pages@v5

      - name: Setup Ruby
        uses: ruby/setup-ruby@v1
        with:
          ruby-version: 3.3
          bundler-cache: true
          
      - name: npm build
        run: npm install && npm run build
        
      - name: Build site
        run: bundle exec jekyll b -d "_site${{ steps.pages.outputs.base_path }}"
        env:
          JEKYLL_ENV: "production"

      - name: Test site
        run: |
          bundle exec htmlproofer _site \
            \-\-disable-external \
            \-\-ignore-urls "/^http:\/\/127.0.0.1/,/^http:\/\/0.0.0.0/,/^http:\/\/localhost/"

      - name: Upload site artifact
        uses: actions/upload-pages-artifact@v3
        with:
          path: "_site${{ steps.pages.outputs.base_path }}"

  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    needs: build
    steps:
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4

```
</details>
(not neccesary to change file name)  
and then delete other unnecessary workflows!

## Problem in Default yml file
The key fixing of workflow is adding
```
- name: npm build
        run: npm install && npm run build
```
before **build jekyll**  
  
So if you want to keep your own configuration, just add the code above inside ```jobs-build-steps``` in front of page building code.  
<img width="360" alt="Screenshot 2025-05-06 at 17 35 37" src="https://github.com/user-attachments/assets/ac7de0ef-8100-4ff3-9254-5dff9a94d7ca" />  
after applying this you can see the workflows became Clean and Beautiful.  
only one log remains after you make changes in the post.
