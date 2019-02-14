---
layout: post
title:      "My First Project - Facebook Open Source Projects CLI"
date:       2019-02-14 21:16:28 +0000
permalink:  my_first_project_-_facebook_open_source_projects_cli
---

A week ago, I hit my one month mark starting the FlatIron Pre-Bootcamp course and two months since I left my last job — Crazy how fast time flies. After a few weeks in the FlatIron Full Stack Web Development Course, I have finally reached my first real project: a CLI Data Gem. 

Sicne I started, and a huge reason why I've started to code, is the idea of Open Source Projects. I've been wanting to contribute to an Open Source Project since I started, so I decided to do this project on Facebook's Open Source Projects. I used Nokogiri to help me scrape through Facebook's Open Source Website, in order to retrieve first the cartegories, and then the projects within each category to be able to see details of each. I'll be walking you through how I built this.

**Step 1: Create your Gem:**

In your terminal, under the folder you would like your gem under, type bundle gem gem_filename. This will set you up with the files you need for a gem. 

**Step 2: Setup your environment and gemspec**

Being new to all of this, this step seemed the most annoying. But having completed the project, I can now tell you that this might be the most important step, so that you can run your project and continously test with no problems. Your environment is where you will "require" or "require_relative" so that your files are all connected and can use each other. Your gemspec is where you will add your dependencies and most importantly where you will get a bit more technical with the actual gem so that you're able to publish it smoothly and don't have any errors raised.

**Step 3: Map out your program in basic English

I think this is a very overlooked step. At least for me, it helps so much to have a sketch or something to build off of before I start coding. I like to make my vision physical so that I don't miss anything and keep myself organized. 

**Step 4: Build your Scrape, CLI, and Objects**

Starting out with your CLI can make it easy to map out your work. And use the previous step here to help you with this. The next step would be to inspect your pages and know what to extract within your scrape methods. After that, you can focus on your Objects and relating them all. 

**Challenges**

Overall, I was fairly content with the way this project resulted. Starting off my main hiccup was finding a website that was easily scrapable. Luckily, after speaking with my Project Coach here at the FlatIron School, she showed me an easy test to see if a site is scrapable or not: https://repl.it/@TheGingertonic/ScraperChecker. 

Additionally, I had a lot of trouble settting up my dependencies with my gem. For some reason I kept coming up with a NameError for the function I wanted to run. After hours of trying to fix it, I realized the error was within the version.rb file which (for obvious reasons) I had blindly ignored it. Luckily, I found the error and fixed it before losing my sanity.

The next big challenge came trying to scrape projects from within a specific category since the categories didn't have their own web page. Normally, it would be very easy if the projects had their own unique URL, but in this case they alI used the same HTML from the main page. So, tried to think of how I can use Nokogiri to only grab only the HTML from that specific category. Also, didn't really get anywhere with that, although I'm sure there's a way. The solution? create a new variable from doc ( doc = Nokogiri::HTML(open("https://opensource.facebook.com/")))  —  id_doc = doc.css("##{category}") and I would pass in a category to my scrape_projects method each time, to make it category specific. 

I had a lot of fun with this project. I'm excited to use these skills and soon make an actual user friendly application. 




