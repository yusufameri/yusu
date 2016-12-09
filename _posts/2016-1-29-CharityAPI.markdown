---
title:  "Making IRS Data Open and Usefull for Non-Profits"
layout: post
date:   2016-1-29 12:24:17 -0500
tag: [Ruby, Charity, IRS, Open Data, Hackathon, API]
projects: true
---

![CharityAPI Logo]({{ site.url }}/assets/images/charityapi.jpg)

### Forward
At my first hackathon [hackathon](http://www.hoyahacks.com/) this year, I visited Georgetown University in Washington DC. The hackathon took place on the weekend of Jan 29, 2016. Here is the original [devpost](https://devpost.com/software/charityapi-qrem6z) that was posted for a project that me and my team worked on.


## We have created an API that collects IRS data on nonprofit organizations
We help make this data more accessible for nonprofit organizations and groups that support them. This has several potential benefits. The API will allow nonprofits and supporting groups to verify their tax exempt status, which will free up resources and allow them to focus on their missions. Current data sources are either slow, requiring you to interact with a user interface to either download a large dataset every two weeks, or search ein by ein. An API will allow groups to integrate automated verification processes into their workflow, freeing up manpower to work on their missions.

An API called Guidestar currently exists, but it charges $4,000 a year, which is a hefty fee for small non-profits and startups. This would provide free access to the data that would be most useful to the users most in need, and who can least afford it. It also opens up an API to data analysts who can help to create new tools to assess and help nonprofits.

## The API will help to make accountability more accessible, allowing users to develop and customize data for their own watchgroups.
The API will also make it easier for users to do analysis that will improve the nonprofit landscape writ large. Data accessibility will make it easier for donors to consider the flow of funds going to different issue areas in different regions. This will allow them to prioritize both on issue importance, and on need. It will also give innovators and entrepreneurs hoping to enter a sector an invaluable tool to both look at hot areas where there is abundant funding, (good for high risk high impact projects,) or to move into underserved areas with low competition, in order to create projects that will get the most bang for their buck.

## What can I do with this data?
The API as it stands is a proof of concept. It was important to us that we host it using tools that will remain accessible after the hackathon ends, and that to prioritize the tool that will make the biggest immediate impact: an API to facilitate automation of verification of nonprofit status, and tax deductibility of donations. There is an immediate demand for this product that is felt in the nonprofit industry, and this will help people right away. That functionality is complete.

But the hosting service is slow, so we weren't able to implement all of the data analytic tools were hoping to. In the short term, we will allow users to query data based on region and detailed categorizations, which will allow users to access data that will benefit prioritization of efforts. Resources allowing, we will also create visualization tools such as heatmaps of funding flows and assets by issue area and region.

## Built With
* ruby
* html
* css
* javascript

### Try it Out
* [GitHub Repo](https://github.com/grantmnelson/charityapi)
* [www.charityapi.org](http://www.charityapi.org)
