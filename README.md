# Analyzing Current Renting Lists on Craigslist 
I’ve been looking to make a move recently. And I want to have a brief understand of current rental pricing lists all over Canada. Therefore, I started to  focus on the population of housing on Craiglist - a popular platform for long-term rental. 

## Web Scraping Craigslist

### My first step is *Getting the Data* 

What I first need is the URL at the first page that want to pull data from added any extra arguments. I need URL for the apt/housing section of all available cities on Craiglist. And then checked the "search titles only",“has image” filter to narrow down the search.

![image](https://user-images.githubusercontent.com/66462812/234837123-d1a73f89-5fc9-42d8-873c-46fc4960b5d9.png)

### Scraping Search Results Beyond the First Page

Here are an example of the "base" URL: 
https://vancouver.craigslist.org/search/apa?availabilityMode=1&hasPic=1&rent_period=3&srchType=T#search=1~gallery~0~0

Since Craigslist only shows 120 results per page, I think of using Selenium as solution. Selenium can also be used to navigate to the next page. Selenium automates web browser interaction from python.
![image](https://user-images.githubusercontent.com/66462812/234835921-aa24e5d9-f819-42af-8ed1-8f62bd763bb0.png)

### Cleaning Data

Following is the data I have extracted from one of the listing pages. 
![image](https://user-images.githubusercontent.com/66462812/234839167-dab56716-a94f-4672-8523-6a778dbe28a3.png)

It's bad that all the information was attached together. Hence, to make use of this chunk information, I added a function called *extract_post_info()* to extrapolate Title/City/Address/Date/Price/Number-of-Bedroom to put them into seperate lists then later into a csv file.

The final result looks like this, which is way more modular and easy to analyze:
![image](https://user-images.githubusercontent.com/66462812/234843754-291133e4-cabc-45b9-9a44-f5d147108760.png)

## Exploratory Data Analysis



