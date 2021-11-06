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

> The profiles that would fulfill the above criteria were considered to:
> * have maintained a considerable activity during 2020
> * have been influencing a large proportion of greek social media user

#### How
* Manual detection and collection of profile names (Rejected)
    > Time consuming procedure
* Creation of a mechanism that would automatically discover new users, moving from one profile to another (Rejected)
    > * High complexity
    > * Detection of many "small" profiles, regarding their followers/subscribers, and difiiculty to find more popular profiles
    > * Strong possibility to find profiles that are not Greek
* Detection of profile names using other corresponding digital sources (Accepted)

#### How
Therefore, the websites mentioned below were utilized:
* www.starngage.com
    > Collected the credentials(user_name, user_id) of popular Greek Instagram profiles 
* www.stats.video
    > Collected the credentials(channel_name, channel_id) of popular Greek YouTube profiles 
* www.socialbakers.com
    > Collected the names of Greek businesses and found their Instagram and/or YouTube profiles

The websites mentioned above provided with arrays that contained information about pouplar Greek content creators and businesses, data that formed the base of our survey.

Mapping the available data | Evaluation of the available for collecting data
---------------------------

#### Typical structure of an Instagram profile:
* **User Name**
* Number of posts
* **Number of followers**
* **Number of following**
* Full Name
* **Profile Category**
* **Biography**
* Instagram Story
* Highlights
* **User Posts**

The fields mentioned in **bold** were collected from each Instagram profile.

#### Typical structure of an Instagram post:
* **Caption**
* **Comments**
* Share Button
* Save Buttom
* **Number of Likes/Video Views**
* **Uplaod Date**
* **Mentioned Users**

The fields mentioned in **bold** were collected from each Instagram post.

#### Typical structure of a YouTube channel:
* **Channel Name**
* **Number of Subscribers**
* External Links
* "Home" Page
* **"Videos" Page**
* "Playlists" Page
* "Community" Page
* "Channels" Page
* "About" Page
* **Channel Videos**
* **Channel ID**
* **Channel Keywords**

The fields mentioned in **bold** were collected from each Instagram post.

#### Typical structure of a YouTube video:
* **Video Title**
* **Number of Views**
* **Upload Date**
* **Number of Likes**
* **Number of Dislikes**
* Share Button
* Save Button
* Description
* **Number of Comments**
* **Duration**
* **Video Keywords**
* **Video Category**
* **Video ID**

The fields mentioned in **bold** were collected from each Instagram post.

Collecting and storing the data | Data collection methods
----------------------------------------

#### Next step:
* Collection and storage of the desirable data

#### Available methods:
* Manual data collection
* Usage of APIs
* Web Scraping
* Questionnaire

>All the above methods were used during the collection of the data

#### Challenges:
* Time consuming manual data collection
* Difficulty of using the provided Instagram API
* Complex source code of YouTube
* Inability to collect interesting but private information

#### Therefore, the steps that we followed are:
1. Collection and storage of popular greek content creators' credentials, implementing web scraping on the websites www.starngage.com and www.stats.video
2. Manual collection and storage of greek businesses' credentials  
3. Collection and storage of the desirable data from each Instagram profile, implementing web scraping
4. Collection and storage of the desirable data from each YouTube channel, using YouTube Data API
5. Collection and storage of additional information, conducting a questionnaire

Collecting and storing the data | Tools
----------------------------------------
1. Data Collection
    * Scrapy Framework
    * YouTube Data API
    * Google Forms
3. Data Storage
    * mongoDB
    * mongoDB Compass
    * mongoDB Atlas
    * mongoDB Charts

Collecting and storing the data | Collection of Instagram and YouTube data
---------------------------------------
#### Instagram data collection | requirements
* Use of Scrapy
* Parallel handling of multiple profiles
* Data extraction from the source code of the platform
* Handling of the pagination of the platform
* Avoidance of being banned, due to anti-scraping mechanisms
    * human behavior simulation (used)
    * use of User Agents
    * HTTP requests analysis (used)
    * dynamic IP address rotation
* Grouping of data in sets and storage
* Frequent code maintenance
* Manual listing of the category of each profile
    * Male
    * Female
    * Other
    * Business
