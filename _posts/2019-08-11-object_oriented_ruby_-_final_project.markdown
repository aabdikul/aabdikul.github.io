---
layout: post
title:      "Object Oriented Ruby - Final Project"
date:       2019-08-11 19:22:57 -0400
permalink:  object_oriented_ruby_-_final_project
---


I wanted to build something that I would find useful so I decided to build a CLI around pulling in stock data. For my program, I pulled in data from MarketWatch, a website that aggregates financial data for different publicly-traded companies. 

I used Bundler extensively, which helped me set up a directory of any and all files I would need to run my program. The most critical of these files was the Gemfile. This allowed me to use the Nokogiri gem to scrape the MarketWatch website. I created a Scraper class and allowed this class to scrape all the pertinent data required: a stock's name, price, beta, dividend, open price, and yield. Once I validated that this scraper method was outputting the values I was looking for in a hash, I moved on to create a Stock class. 

My Stock class leveraged the hash I created in my Scraper class and allowed me to access these values as attributes. I then moved on to created my final file, the CLI. In this CLI, I created outputs that allowed the program to interact with the user by outputting different phrases and allowing the user to engage by typing in a stock ticker symbol. 

The stock ticker symbol becomes the key piece of interaction as it lets the user pull in the values that they're looking for individually. If they want to see a full scope of information in a snapshot form, they can type in an "info" command and are given a readout of that stock at a high level. 

My gem's name is QuickerTicker. Check it out at: https://github.com/aabdikul/quicker_ticker. 
