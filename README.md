# Analyzing Current Rental Listings on Craigslist
I have been actively searching for a new place to live and wanted to gain a better understanding of the current rental pricing for apartments and condos in Canada. To accomplish this, I decided to focus on the housing population listed on Craigslist, a popular platform for long-term rentals.

## Web Scraping Craigslist

### My first step is *Getting the Data* 
To begin, I needed the URL for the first page from which I wanted to pull data, without any additional arguments. Initially, I selected the "apt/housing" section and applied filters such as "has image," "condo," and "apartment" to narrow down the search. Let's start by examining the listings in the Vancouver area!

I employed web scraping techniques to retrieve search results beyond the first page. Here's an example of the "base" URL:
https://vancouver.craigslist.org/search/apa?hasPic=1&housing_type=1&housing_type=2#search=1~list~0~0

Since Craigslist displays only 120 results per page, I utilized Selenium as a solution. Selenium enables automated web browser interaction with Python, allowing me to navigate to the next page.

![image](https://user-images.githubusercontent.com/66462812/234835921-aa24e5d9-f819-42af-8ed1-8f62bd763bb0.png)

## Cleaning and Manipulating Data

### Developing a Function for Accurate Data Extraction

Following is the data I have extracted from one of the listing pages. 
![image](https://user-images.githubusercontent.com/66462812/234839167-dab56716-a94f-4672-8523-6a778dbe28a3.png)

To extract meaningful information, I developed a function called extract_post_info(). The function effectively separated the attached information, including Title, City, Address, Date, Price, and Number of Bedrooms, into separate lists. These lists were later compiled into a CSV file for easier analysis.

### Further Cleaning

1. Removed duplicated postings
2.Filtered postings to include only those with 1, 2, or 3 bedrooms, as apartments with four or more bedrooms are very rare
3.Converted Square Feet to NaN when the value exceeded 3000, as most apartments do not exceed that size

![image](https://user-images.githubusercontent.com/66462812/234918006-444b4bd4-9cc7-4c75-9b51-ae6b44a19a43.png)

### Removing Outliers

I removed outliers from the dataset to minimize their impact on statistical analyses and prevent skewed results. Most outliers postings was listed by wrong-category-housing/input by mistake 

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

## Exploring Apartments All Over Canada

The script I developed can be easily modified to gather data from any region, category, or property type on Craigslist. By simply changing the base URL to the desired city, we can obtain rental information from various locations. In the script, I have already grouped cities other than Vancouver and Toronto to minimize the need for repetitive execution:

![image](https://user-images.githubusercontent.com/66462812/234837123-d1a73f89-5fc9-42d8-873c-46fc4960b5d9.png)

After collecting data from multiple cities, I imported the dataset into Tableau to create an interactive visualization. You can explore the visualization using the following link:

https://public.tableau.com/views/AnalyzingCurrentRentingListsonCraigslist/Dashboard?:language=en-US&:display_count=n&:origin=viz_share_link
This visualization provides a comprehensive overview of rental listings across Canada, allowing you to compare and analyze various cities.













