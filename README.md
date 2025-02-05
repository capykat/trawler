<!--THIS FILE IS AUTOGENERATED, TO UPDATE ITS CONTENT, UPDATE THE README.template.md IN THE docs DIR-->
<center>

<h1>Trawler</h1>

<img src="src/assets/icon.svg">

A job scheduler and analysis tool for webscraping (and other) tasks.

</center>

![Node.js Package](https://github.com/niczem/trawler/workflows/Node.js%20Package/badge.svg)

## Datasources
   

Curently the following datasources are implemented:


   - **facebook posts and reactions**
   scrape facebook posts, comments and reactions (like, heart, etc)
   - **gab (nazi-twitter)**
   crawl posts for user
   - **google dorking**
   find interesting files and download them
   - **url**
   generic http scraper
   - **mail**
   sends mails and files - mostly usefull in pipelines
   - **masscan**
   udp based port scanner (requires docker)
   - **onionlist**
   download tor-catalogue from onionlist.org
   - **tiktok**
   get video metadata per hashtag, download them and analyse the text using easyOCR
   - **url**
   generic http scraper

### Create your own datasource
    - copy template dir in ./jobs
    - define fields in fields.js which are needed to start the job
    - a job can output one or multiple files
    - no directories should be used, please use archives
    - use job_id.ext (eg job_id.json) as filename

## Features
- simple configuration of actions/datasources, also from 3rd party modules/repos
- job monitoring and scheduling
- schedule jobs
- sqlite, csv and json browser
- separation of datasets/artifacts (one archive per crawl)
- scalable amount of workers (also on other machines)

## Architecture
### Frontend and API
- GUI to create and schedule jobs
- Displays pending, running and done jobs
- Display csv and sqlite datasets

### Worker(s)
- Can be distributed (workers and c&c on different locations/servers)
- Jobs are managed through json files (and can be distrubuted with an adapter like pouchDB)
- Multithreaded


## Install & run

### Using NPM

```
git clone https://github.com/niczem/trawler.git --recurse-submodules
cd trawler
npm i
npm run all
```
