<h1 align="center">

<img src="./screenshots/iterative.png" alt="logo" width="150" />

<br>
<br>

Notion Board

</h1>

## Table of contents
- [Introduction](#introduction)
- [Inputs](#inputs)
- [Usage](#usage)
- [Screenshot](#screenshot)

## Introduction 
This action lets you sync your GitHub issue with your notion board. Currently it syncs issue state and labels. 

> More feature on the way.

## Inputs

|input|description|required|
|-----|-----------|--------|
|`NOTION_API_KEY`|your notion api key|`true`|
|`NOTION_DATABASE`|your notion database id|`true`|
|`GITHUB_TOKEN`|your github token|`true`|

## Usage
```yml
name: Notion Board
on:
  issues:
  issue_comment:
jobs:
  notion:
    runs-on: ubuntu-latest
    steps:
      - uses: actions/checkout@v2
      - name: Notion Board
        uses: Souvikns/Notion-Board@v1.0.0
        env: 
          GITHUB_TOKEN: ${{ secrets.GITHUB_TOKEN }}
          NOTION_API_KEY: ${{ secrets.NOTION_API_KEY }}
          NOTION_DATABASE: ${{ secrets.NOTION_DATABASE }}
```

As of now notion API does not allow creating or changing properties, so right now you have to add these properties manually to use this action. 
- URL - type: `URL`
- id - type: `Number`
- state - type: `Select`
- labels - type: `Mutli-Select`

## Screenshot
![board](./screenshots/notion-board.PNG)
