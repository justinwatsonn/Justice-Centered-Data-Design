```md
# Midterm - Justin Watson

- **Name**: Justin Watson
- **Dataset**: Meta Ads

## Overview

I chose the dataset because I think it is somewhat relevant to things that are going on today, and I thought it was an interesting dataset to look at. 

```js
import {utcParse,utcFormat} from "d3-time-format";
```



## Attach the data

```js

const data = FileAttachment("../data/midterm-options/meta-ads/meta-ads-mentioning-israel-after-2015-09-11.csv").csv({typed: true})


```


## Convert Dates
```js

const parseDate = d3.utcParse("%Y-%m-%d")

```

## Grouping #1 - Page Name

My plan is to group the data by the advertiser's page name. This will allow me to count the total number of ads each advertiser has run that mention "Israel". The goal is to identify the most active pages. 

Provide a procedure of your grouping plan in an ordered list before the codeblock:

1. Use d3.rollup on data
2. Use the page_name to group the ads
3. Calculate the length of the array of items, giving the total count of Ads per page.

Again, be sure to output your newly transformed data in executable codeblocks
for easier verification and reviewing.

```js

const adsPerPage = d3.rollup(
    data,
    (d) => d.length,
    (d) => d.page_name
)
```
```js
adsPerPage



```
## Grouping #2 - Time

For this grouping, I want to analyze the distribution of the ads over time. By grouping the ads by their day, I can identify trends, such as whether the volume of ads increases during election cycles or other unique periods. 

Provide a procedure of your grouping plan in an ordered list before the codeblock:

1. adsPerDay stores the counts
2. Iterate through the data using a for loop.
3. For each ad, get the full year.

Again, be sure to output your newly transformed data in executable codeblocks
for easier verification and reviewing.

```js


const adsPerDay = d3.rollup(
    data,
    (d) => d.length,
    (d) => d.ad_creation_time
)

```

```js
adsPerDay
```

## Reflection

Use the following prompt to guide your reflection about your data work:
"What 2-3 insights and 2-3 questions did you glean from your initial work
with the dataset?"

Use the PR-TEMPLATE prompts to reflect on the midterm experience.

Insights

1. AIPAC was #1 in terms of headlines. Jewish Voice Ministries International also dominated the headlines. I wanted to find a platform that stood out in terms of the number of ads.
2. Although there was a lot of overlap, there was still a good variety of different pages pushing ads. 21208 to be exact.


Questions
1. How was this data scraped?
2. How does this data look now in 2025?

```


