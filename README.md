# Learn to Code: Introduction Web Scraping

Brought to you by Galvanize. Learn more about the way we teach at [galvanize.com](http://galvanize.com).

Get to this repo by typing in URL: **scrape.sage.codes**

### FAQ: 

- WIFI: `Galvanize Guest` | Password: `beapineapple`
- Bathrooms: Behind you down the hall to the left
- Kitchen outside back classroom door with Coffee & Tea!
- Snacks + water in back of room

## What this workshop is

A super friendly introduction to web scraping. No previous experience expected, but some concepts may be confusing if you have never programmed before. If you get too lost, let me know!

You can't learn EVERYTHING in ~2 hours. But you can learn enough to get excited and comfortable to keep working and learning on your own! 

- This course is for absolute beginners
- Ask Questions!
- Answer Questions!
- Help others when you can
- Its ok to get stuck, just ask for help!
- Feel free to move ahead
- Be patient and nice




## Setting up your computer


#### Please set up the following:

* A web browser to see what we're working on as others see it (Recommend Google Chrome: [chrome.google.com] (http://chrome.google.com))

* We will be using a google colaboratory notebook for this workshop, so you'll need access to a google drive where you can edit and save. You can sign up here if you don't already have a google account: [www.google.com/drive/](https://www.google.com/drive/)


Well... that was easy! 


## Overview
The goal of this brief course is to provide you with a fun introduction to web scraping using Python.

#### Here's what we'll be doing:
* A primer on some technologies we're going to use
* Building a simple web scraper with Python
* I'll leave you with a couple challenges at the end. You can try to complete them here if we have time or try them at home!


## About me:
I'm Thomas Adams. I'm a data scientist with a background in science, languages, and music and a graduate of the Galvanize Data Science Immersive program. Previously, I've taught a variety of subjects at the middle and high school levels. I love making tools and solving problems, finding hidden connections in all things, and helping others build their understanding and capabilities. I'm currently exploring projects involving the intersection of data science with game design as well as different applications of artificial neural networks. I'm happy to correspond with any of you about data science, Galvanize, chemistry, linguistics, brain science, game design, music, etc. I'd love to hear from you:

- LinkedIn: [CowardlyBattleCat](https://www.linkedin.com/in/cowardlybattlecat/)
- GitHub: [CowardlyBattleCat](https://github.com/CowardlyBattleCat)
- Email: [thomas.harlan.adams@gmail.com](mailto:thomas.harlan.adams@gmail.com)

I've adapted the curriculum for this workshop from materials created by [Sage Elliott](http://sageelliott.com/), a Technology Evangelist here at Galvanize. Sage is awesome! Check out his work and reach out to him if you have questions:

- LinkedIn: [sageelliott](https://www.linkedin.com/in/sageelliott/) 
- GitHub: [sagecodes](https://github.com/sagecodes)
- Email: [sage.elliott@galvanize.com](mailto:sage.elliott@galvanize.com)


## About you!

Give a quick Intro!

- Whats your name?
- Whats your background?
- Why are you interested in Web Scraping?


## Web Scraping

### What is it?
I usually describe it as using a program to get data from the web by pulling content without an API (Application Program Interface).

Many sites have APIs you can connect to and use to pull data. The [Twitter API](https://developer.twitter.com/en/docs.html) is a nice example. APIs can be used to gather weather data, sports scores, ebay listings and more. This is great! Sometimes, however, you need data from a site that doesn't have an API. Thats what we're going to look at in this workshop. 


### Where is it used?

Really anywhere you think it would be interesting or useful to gather data. 

Some people I've met have built web scrapers to look for jobs & find apartments.

Organizations may search for email or contact information.

Companies might perform competitive analysis on a competing company to find their listings and prices.

Realtors can scrape housing listings.

Market researchers will investigate sentiment and words in reviews.

Anytime you want data!


## Before we build

### HTML Basics

HTML is one of the main building blocks of the web! Don't worry about memorizing all of this if it's unfamiliar, but feel free to use this a quick reference to make sense the stuff we'll be seeing.

###### Some common Tags(Elements):

- `<html>`	designates an HTML document
- `<head>`	contains undisplayed information about the document
- `<title>`	Creates a title for the document
- `<body>`	contains displayed information
- `<header>, <main>, <footer>` denote which part of the page elements belong to

- `<h1> - <h6>` create section headings (h1 biggest, h6 Smallest)
- `<p>` creates paragraphs
- `<a href=""></a>` (anchor), activates a link in the page
- `<ul>, <ol>` creates lists
  - `<li>` contains items in lists
- `<br>`	Inserts a single line break


###### Self-closing Tags:
most HTML tags require an opening and a closing tag. There are a few however that do not:

- `<img src="">` creates an image in the page
- `<br>` creates a break in the content
- `<input type="">` creates an input field
- `<hr>`	Creates a line in the page 

###### IDs, Classes
IDs and classes are very similar.
These are used to target specific elements (you'll see more examples in the CSS section).

- `<h1 id="profile-header"></h1>`
- `<h1 class="subject-header"></h1>`

- IDs should only be used once on a page. IDs can also be used to bring the user to a specific part of the page. `your-site/#profile-picture` will load the page near the profile picture. 
- Classes can be used multiple times on a page. 


See More tags [here](https://www.w3schools.com/tags/ref_byfunc.asp)

Learn more HTML [here](https://www.w3schools.com/Html/)

	
#### Inspect element of a web page

- Go to a web page
- right click
- select `inspect element	`
- you should now see a pop up or frame showing the HTML of a web page.


### Python

We're going to be using python to do our web scraping.

Don't worry if you've never programmed in python or at all before! I will explain concepts along the way. And if you want me to repeat something just ask. We'll be doing a free intro to python workshop in February too if you want to go deeper! Or go through our [free data science prep material](https://www.galvanize.com/data-science-prep).

##### Requests

We will use the [Requests](http://docs.python-requests.org/en/master/) module to visit a URL and get web elements. 

##### Beautiful Soup

We will use [Beautiful Soup](https://www.crummy.com/software/BeautifulSoup/) to parse HTML and extract the information we need.


##### Pandas

We'll use [pandas](https://pandas.pydata.org/) to do some analysis and visulizations on our data 

##### NLTK

We'll use [NLTK](https://www.nltk.org/)(Natural Language Toolkit) to do some simple natural language processing on some text. 

##### Google Colab

We'll use google collab as our editor. It comes preinstalled with everything we need, including the 4 modules mentioned above!


## Lets scrape data from the web!

Here's what we will do!

- Look at data tags
- write code to get data
- Look at scraped data
- get specific parts of the data
- transform the data for different use case
- minor visulizations for the data so we can understand it better
- Basic Sentiment Analysis on headlines to see how negative they are


#### Get Started:

- Open the notebook for this workshop [here](https://colab.research.google.com/drive/1UzyruU8hLorhEZb4RmHqh7pMQjt7mDeQ).

Make a copy by clicking `file` and `make copy` or `save to drive`


# Awesome, you now know the basics of web scraping!

Book mark this repo or the colla notebook and experiement with the code. Try a different website. 


## Challenges

- Install Python and run this scraper locally
- Scrape a different site
- Visiualise your data better using [matplotlib](https://matplotlib.org/)
- Save your data to a file or database
- Sentiment analysis on headlines like Google news


# Keep Learning

- [Free Data Science Prep](https://www.galvanize.com/data-science-prep)



- Checkout [Scrapy](https://scrapy.org/). Another python module foring doing web scraping. 




## Upcoming Events!

We host so many events! check out our [calendar](https://www.galvanize.com/events)

Visit the [Learn to code Seattle](https://www.meetup.com/Learn-Code-Seattle/) meetup for all upcoming events.


## What is Galvanize?
###### We are a community!


#### Immersive Bootcamp

- [Data Science](https://www.galvanize.com/data-science) - 5/6/19 - 8/2/19 

- [Software Engineer](https://www.galvanize.com/web-development) - 2/19/19 - 5/17/19

#### Part-Time Courses

- [Data Analytics](https://www.galvanize.com/part-time/data-analytics) 2/12/19 - 5/2/19
- [Python Fundamentals](https://www.galvanize.com/part-time/data-science-fundamentals) - 2/20/19 - 3/29/19

#### Co-working Space

[work in our building!](https://www.galvanize.com/entrepreneur)

#### We are a community

## Questions

Please feel free to reach out to me with any questions! Let me know what you're planning to do next and how I can help!


- Website: [sageelliott.com](http://sageelliott.com/)
- Twitter: [@sagecodes](https://twitter.com/@sagecodes)
- LinkedIn: [sageelliott](https://www.linkedin.com/in/sageelliott/) 
- Email: [sage.elliott@galvanize.com](mailto:sage.elliott@galvanize.com)






