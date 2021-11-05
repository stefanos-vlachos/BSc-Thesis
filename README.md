# University_Thesis
From digital footprints to facts: mining social data for marketing practices
============================================================================

Overview
---------
This repository provides access to the survey that was conducted by me and Dimitrios Ioannis Linarakis in the context of our university thesis, whose aim was to collect public data from popular Greek Instagram and YouTube profiles and draw conclusions about:
1. the digital behavior and preferences of the Greek Instagram and YouTube community
2. the activity of Greek businesses on social media
3. the impact of COVID-19 on the digital behavior of the users

The present repository provides insight into all the successive steps that were followed during our survey as well as the final conclusions that were drawn.

Introduction | Problem Analysis
-------------------------------

#### Observations

1. rapid growth of the social media & dominance in our daily lives
2. intense activity of the users on social media & development of digital relationships
3. businesses are given the chance to engage with a wider crowd
4. more and more businesses are turning to social media & developing their digital precenses
5. high popularity of Instagram & YouTube during 2020

#### Questions

1. How can businesses approach the social media users more efficiently?
2. What is it that preserves the interest of the users in high levels?
3. With which type of content do the users engage more?

Introduction | Our contribution
-------------------------------
We searched for answers:

#### Mapping the available data

1. Detection of Instagram and YouTube profiles
2. Evaluation of the available for collecting data

#### Collecting the data

1. Collection and storage of data extracted from 2.727 public Instagram profiles
2. Collection and storage of data extracted from 2.057 public YouTube profiles
3. Collection and storage of the answers of 270 people that participated to a corresponding questionnaire

#### Drawing conclusions

1. Study of the collected data
2. Creation of charts
3. Conclusions being drawn about:
* the digital behavior and preferences of the Greek Instagram and YouTube community
* the activity of Greek businesses on social media
* the impact of COVID-19 on the digital behavior of the users

Mapping the available data | Detection of Instagram and YouTube profiles
---------------------------

#### Initial step of the research process

* Detection of profiles that would form the basis of the research

#### Criteria

* **Instagram profiles**: number of followers >= 1000
* **YouTube profiles**: number of subscribers >= 5000
* Greek non-private profiles
* Profiles that have uploaded at least one post during 2020

>The profiles that would fulfill the above criteria were considered to:
>* have maintained a considerable activity during 2020
>* have been influencing a large proportion of greek social media user

#### How
* Manual detection and collection of profile names
* Creation of a mechanism that would automatically discover new users, moving from one profile to another 
* Detection of profile names on other corresponding digital sources

#### Structure
---------------------------

This web scraper has the basic stracture of a Scrapy spider with the addition of two folders: 
* the "resources" folder 
    >created to store files that contain important data for the scraping mechanism, such as names of Instagram profiles.
* the "tools" folder.
    >created to store files that contain usually used functions, such as functions that carry out the communication with the database.

####  Features
-----------------------------

The provided web scraper reads as input usernames of Instagram users from:
* a database collection
* a JSON file 
    >located in the "resources" folder


Due to the fact that this mechanism was created in the context of my thesis, it has a few specific features:
* it scrapes profiles with a number of followers higher than 1.000 
* it scrapes profiles that have uploaded at least one post in 2020
* it scrapes only the posts that were uploaded during the year 2020
* it is based on the personalised parametrisation of the "settings.py" file, in order to avoid anti-scraping blocking 
* it works attaching custom request headers to the sent requests, including the Cookies field for each session
    >All the above parameters can be modified.


From each profile, the scraping mechanism collects:
* General Information:
    * **User Name**
    * **User ID**
    * **Account Type/Category**
    * **Gender**
        >It was manually populated, beacause Instagram does not provide this field
    * **Number of followers**
    * **Number of followings**
    * **Number of posts**
    * **Number of videos**
* Fields of each uploaded post:
    * **Post ID**
    * **Post Type** 
        >Photo, Video or Slideshow
    * **Upload Date**
    * **Number of Likes**
    * **Number of Comments**
    * **Number of Views**
        >in case of Video post
    * **Tagged Users**
    * **Hashtags**
* Fields of each slide in a Slideshow:
    * **Slide ID**
    * **Slide Type**
    * **Slide Views**
        >in case of Video slide


The mechanism also calculates additional metrics that help with reflecting the popularity of the collected Instagram profiles and posts:
* Post level metrics:
    * **er_view**
        >(Number of Likes / Number of Views of a video) * 100
    * **er_post**
        >(Number of Likes / Number of followers) * 100
    * **er_comments post**
        >((Number of Likes + Number of Comments) / Number of followers) * 100
* Account level metrics:
    * **avg_likes**
        >Average number of Likes, based on the collected posts
    * **avg_comments**
        >Average number of Comments, based on the collected posts
    * **avg_engagement**
        >Average er_comments_post, based on the collected posts
    * **avg_days_between_posts**
        >Average upload frequency of the account, based on the collected posts


In order to handle Instagram's tactic that divides the posts of each account at subsections of 12 posts, the collection of the fields mentioned above was completed via two methods:
* **parse()**
    >Handles the first 12 posts of each account
* **parse_pages()**
    >Handles the next dozens of posts of each account


As soon as all the necessary fields have been collected, they are being grouped and stored as documents in the MongoDB database, using the file "pipelines.py". The structure of each document is declared in the "items.py" file and it is as follows:
* **personal_info**
    >An object containing all the collected general information of an account mentioned above
* **tagged_users**
    >An object containing all the unique users that have been mentioned in the collected posts of an account
* **hashtags**
    >An object containing all the unique hashtags that have been mentioned in the collected posts of an account
* **user_posts**
    >An array containing the fields of all the collected posts of an account 

How to Use
---------------------------
1. Download the project
2. Open the file "instagram_spider.py" that is located in the folder "spiders"
3. Update the variable "request_header", based on the request headers that your browser sends to Instagram
    >This field can be found selecting one of the sent requests in the section "Network", while inspecting an Instagram account
4. Update the variable "mozilla_cookies", based on the "Cookies" field that your browser attaches to the sent requests
    >This field can be found selecting one of the sent requests in the section "Network", while inspecting an Instagram account
5. Comment/Uncomment one of the provided methods to populate the list "users_to_scrape"
    >Import names from file or database
6. Open the file "pipelines.py"
7. Upload the variables "myclient", "db" and "collection", based on the address of your database
8. Open the file "documents_exporter.py", located in the folder "tools"
9. Upload the variables "myclient", "db" and "collection", based on the address of your database
10. Open Command Line
11. **cd** to the path of the project
12. Run:
```
scrapy crawl InstagramSpider
```
