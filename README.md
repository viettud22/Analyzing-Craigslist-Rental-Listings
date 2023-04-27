# Analyzing Current Renting Lists on Craigslist 
I’ve been looking to make a move recently. And I want to have a brief understand of current rental pricing lists all over Canada. Therefore, I started to focus on the population of housing on Craiglist - a popular platform for long-term rental. 

## Web Scraping Craigslist

### My first step is *Getting the Data* 

What I first need is the URL at the first page that want to pull data from added any extra arguments. I need URL for the apt/housing section of all available cities on Craiglist. And then checked the “has image”,"condo" and "apartment" filter to narrow down the search.

![image](https://user-images.githubusercontent.com/66462812/234837123-d1a73f89-5fc9-42d8-873c-46fc4960b5d9.png)

### Scraping Search Results Beyond the First Page

Here are an example of the "base" URL: 
https://vancouver.craigslist.org/search/apa?hasPic=1&housing_type=1&housing_type=2#search=1~list~0~0

Since Craigslist only shows 120 results per page, I think of using Selenium as solution. Selenium can also be used to navigate to the next page. Selenium automates web browser interaction from python.
![image](https://user-images.githubusercontent.com/66462812/234835921-aa24e5d9-f819-42af-8ed1-8f62bd763bb0.png)

## Cleaning and Manipulating Data

### Developed function with significant accuracy to extract meaningful data
Following is the data I have extracted from one of the listing pages. 
![image](https://user-images.githubusercontent.com/66462812/234839167-dab56716-a94f-4672-8523-6a778dbe28a3.png)

It's bad that all the information was attached together. Hence, to make use of this chunk information, I added a function called *extract_post_info()* to extrapolate Title/City/Address/Date/Price/Number-of-Bedroom to put them into seperate lists then later into a csv file.

### Further Cleaning
1. Drop duplicated postings
2. Keep only postings of 1/2/3 bedrooms since apartments with four or more bedrooms are very rare
3. Convert Square Feet to Nan when its more than 3000 because most apartment size can't exceed 3000sqft
![image](https://user-images.githubusercontent.com/66462812/234918006-444b4bd4-9cc7-4c75-9b51-ae6b44a19a43.png)

### Remove Outliers
I removed outliers because it can have a big impact on statistical analyses and skew the results. Most outliers postings was listed by wrong-category-housing/input by mistake 

![image](https://user-images.githubusercontent.com/66462812/234915688-961eddc4-6ea9-401e-b306-6212219a2d2d.png)

The final result looks like this, which is way more modular and easy to analyze:
![image](https://user-images.githubusercontent.com/66462812/234843754-291133e4-cabc-45b9-9a44-f5d147108760.png)

## Exploratory Data Analysis

![image](https://user-images.githubusercontent.com/66462812/234920035-5cadcc8f-c912-40c3-9b53-34c56b94d4c2.png)

![image](https://user-images.githubusercontent.com/66462812/234920121-84e1151e-4d01-4754-949d-7da52fe14bde.png)

![image](https://user-images.githubusercontent.com/66462812/234919928-adb960a3-88cb-45f9-b161-b124787a0d47.png)

![image](https://user-images.githubusercontent.com/66462812/234919967-dc941da6-0d81-414f-bc47-1693d74e3178.png)

![image](https://user-images.githubusercontent.com/66462812/234919994-266672fd-e758-4d71-a383-52bc78bcdd5f.png)

![image](https://user-images.githubusercontent.com/66462812/234920200-459aae04-5e03-4a4c-b9c7-64362b89dafd.png)

![image](https://user-images.githubusercontent.com/66462812/234920370-dd00ab14-5847-416d-b59f-a865a35b8883.png)







