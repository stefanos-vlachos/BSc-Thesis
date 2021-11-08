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
#### Instagram data collection | Requirements
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
    * Male (784 profiles)
    * Female (926 profiles)
    * Other (767 profiles)
    * Business (249 profiles)

#### Instagram data collection | Code
The scraping mechanism that we developed in order to collect data from Instagran can be found at https://github.com/stefanos-vlachos/Instagram_Scrapy_Scraper.

#### YouTube data collection | Requirements
* Communication between Scrapy and YouTube Data API
* Use of multiple API keys
* Parellel handling of multiple profiles
* Handling of the pagination of the platform
* Special handling of videos that keep various fields private
* Grouping of data in sets and storage
* Manual listing of the category of each profile
    * Male (782 profiles)
    * Female (318 profiles)
    * Other (654 profiles)
    * Business (303 profiles)

#### YouTube data collection | Code
The scraping mechanism that we developed in order to collect data from YouTube can be found at https://github.com/stefanos-vlachos/Youtube_Scrapy_Scraper.

Collecting and storing the data | Questionnaire
-------------------------------------

#### Need for:
* Collection of data that could not be retireved from the social media platforms
* Assessment of representativity of the already collected data

#### Conduction of a questionnaire:
* **Aim** | Assessment of representativity and augmentation of the drawn conclusions
* **Tool** | Google forms
* **Target Group** | People from a broad age and social range

Study of the collected data and final results | Introduction
-----------------------------

#### Goals
* Conclusions about the digital behavior and the preferences of the Greek Instagram community
* Conclusions about the digital behavior and the preferences of the Greek YouTube community
* Factors that affect the performance of the publicized posts
* Activity of Greek bussinesses on social media
* Impact of COVID-19 on social media

#### Challenges
* Effective time management
* Large volume of data
* Handling of outliers
* Objective approach to the data
* Consolidation of the drawn conclusions

#### Steps
1. Creation of charts and drawing of conclusions about Instagran, using MongoDB Charts
2. Creation of charts and drawing of conclusions about YouTube, using MongoDB Charts
3. Creation of charts and drawing of conclusions, studying the answers to our questionnaire via Google Forms
4. Cross-checking of all the above conclusions

> Uilisation of post and profile hashtags playd a crucial role at drawing the final conclusions.

Study of the collected data and final results | Secondary variables
-----------------------------
* Variables that resulted as a function of already collected data
* Helped at the detection of complex correlations
* Helped at the more accurate representation of the performance of a post
* Helped at detecting the outliers

#### Secondary variables | Instagram:
* Engagement Rate Post
* Engagement Rate Comments Post
* Engagement Rate Views
* Average days betwwen posts

> For a more detailed description of the secondary variables regarding Instagram, you can visit https://github.com/stefanos-vlachos/Instagram_Scrapy_Scraper

#### Secondary variables | YouTube:
* Video Dislikes Ratio
* Video Engagement
* Views Subscribers Ratio

> For a more detailed description of the secondary variables regarding Youtube, you can visit https://github.com/stefanos-vlachos/Youtube_Scrapy_Scraper

Study of the collected data and final results | Conclusions about Instagram
-----------------------------

#### General Conclusions
* It is a platform with a pure social networking foundation
* Photographs play the principal role of the platform
* Better establishment in younger ages
* Increasing influence on users from a broad age range
* High frequency of creating and consuming content

#### Impact of different account categories
* Particular interest for female creators
* Enhanced engagement between audience and personalized accounts, in contrast with business and other accounts
* Strict and professional character of business accounts
* Male users tend to follow more accounts beside the other account categories

#### Productivity
* Principal role of business accounts and female creators
* Less productive male creators
* High activity of male and female users during the summer months
* Prosperity of:
    * lifestyle (males, females)
    * traveling (males)
    * fashion/beauty (females)
* "Other" type accounts produced more content related to:
    * traveling
    * arts
    * entertainment

#### Impact of different content types
* Wide interest in:
    * lifestyle/publicization of daily, personal moments
    * traveling
    * arts
    * entertainment
* Males are also interested in:
    * sports
    * tenchnology and science
* Females are also interested in:
    * fashion/beauty
    * cooking
* High impact of Giveaways
    * organised by numerous creators of different age and interests
    * engagement of users from a wide age range

Study of the collected data and final results | Conclusions about YouTube
-----------------------------
#### General Conclusions
* The publicization and watch of videos plays the principal role of the platform
* Gradula adoption of modern social media characteristics, like stories 
* Big establishment in the Greek community, due to its multiannual presence
* Better establishment of the modernisation of the platform in the younger ages
* Lower frequency of content creation and consumption, compared to Instagram

#### Impact of different channel categories
* Higher activity of male creators and "Other" channels
* Female creators aim at a less wide audience
* Low and often negative engagement between the audience and the business channels
* Enhanced engagement between audience and personalized channels, in contrast with businesses and "Other" channels
* Enhanced engagement between audience and newly established channels

#### Productivity
* Principal role of male creators and "Other" channels
* Increase in creators' productivity during 2020
* Low frequency of content production during the summer months
* Prosperity of:
    * gaming
    * music
    * entertainment
    * comedy
    * news and politics
    > The last 3 categories reported a remarkable increase in productivity during 2020
* Tendency of male creators and "Other" channels towards:
    * gaming
    * music
    * comedy
* Tendency of female creators towards:
    * lifestyle
    * fashion/beauty
    * cooking
* Various content categories created by business channels, such as:
    * comedy
    * gaming
    * fitness
    * technology and science
   
#### Impact of different content types
* Wide interest in:
    * gaming
    * comedy
    * entertainment
    * arts
    * educational content
* Audience's warm relationship with:
    * gaming
    * fashion/beauty
    * pets and animals
* Low and often negative engagement between the audience and :
    * news and politics
* Modern trends:
    * entertainment
    * gaming
    * people and blogs
* Growth dynamics of:
    * music
    * science and technology
    * sports
    * fashion/beauty
* Males are more interested in:
    * gaming
    * sports
* Females are more interested in:
    * lifestyle
    * fashion/beauty
    * cooking
* High impact of Giveaways
* High impact of videos that require the audience's active participation, like QnAs, Challenges or "We read your comments..." type videos
* High impact of videos that show the daily routine of a creator, like Vlogs

Study of the collected data and final results | More general observations
-----------------------------
* Bigger use of social media from younger users:
    * older users: more purposeful use of social media
    * younger users: use of social media without a strictly defined purpose
* Higher engagement between the audience and content during the summer and Christmas
* The performance of the posts seemed to benefit from:
    * the use of hashtags
    * the collaboration of creators
    * the sharing of the content by the audience
* Prefernce of the audience for milder frequencies of uploading content

Study of the collected data and final results | Business sector and influencer marketing
---------------------
#### General
* Activity of numerous businesses on social media
* Instagram provides a fruitful ground for developing trade relations
* Remarkable but lower activity of businesses on YouTube
* Businesses have not succeeded to develop a warm relationship with the audience through social media
* Common tactics:
    * Strict and professional character of bussiness accounts
    * High activity during holiday seasons, celebrations and anniversaries
    * Promotion via in person advertising or influencer marketing

#### In person advertising
* Less fruitfull tactic
* Low engagement between the audience and the advertised product
* Higher tolerance of the Instagram community for advertisements
* Bigger establishment of advertisements in older ages

#### Influencer marketing
* More fruitfull tactic
* Businesses turn to popular content creators to promote their products
* Very high engagement rate between the audience and posts that contain the promotion of a product by an influencer
* Bigger establishment of influencer marketing in younger ages

#### Businesses orientation
* Businesses on Instagram:
    * ususally turn to female creators in order to be promoted
    * are highly active in the sectors of fashion and beauty
    * aim to users from a wide age range 
    
* Businesses on YouTube:
    * ususally turn to male creators in order to be promoted
    * are highly active in the sectors of gaming, science, technology, fashion/beauty, and traveling
    * aim to younger users
  
Study of the collected data and final results | COVID-19
-----------------------
* Direct impact on the Greek social media users' psychology
* People turnt to social media during the pandemic
* Numerous hashtags related to the pandemic were widely used
* The first wave of COVID-19 seemed to have affected the greek community in a larger extend than the second one
* There was an important increase in the productivity of YouTube videos during the pandemic
* Businesses and "Other" accounts boosted their digital presence on social media
* Many content categories reported notable growth:
    * gaming
    * entertainment
    * comedy
    * news & politics
