
# Web Scraping 

## Web Scrape with Python in 4 minutes 

***Web scraping is a technique to automatically access and extract large amounts of information from a website, which can save a huge amount of time and effort.***

### Important notes about web scraping: 

1. Read through the website’s Terms and Conditions to understand how you can legally use the data.
2. Make sure you are not downloading data at too rapid a rate because this may break the website.

## What is Web Scraping ?

***Web scraping, web harvesting, or web data extraction is data scraping used for extracting data from websites. The web scraping software may directly access the World Wide Web using the Hypertext Transfer Protocol or a web browser. While web scraping can be done manually by a software user, the term typically refers to automated processes implemented using a bot or web crawler. It is a form of copying in which specific data is gathered and copied from the web, typically into a central local database or spreadsheet.***

***Web scraping a web page involves fetching it and extracting from it. Fetching is the downloading of a page (which a browser does when a user views a page). Therefore, web crawling is a main component of web scraping, to fetch pages for later processing. Once fetched, then extraction can take place. The content of a page may be parsed, searched, reformatted, its data copied into a spreadsheet or loaded into a database. Web scrapers typically take something out of a page, to make use of it for another purpose somewhere else. An example would be to find and copy names and telephone numbers, or companies and their URLs, or e-mail addresses to a list.***

***Web scraping is used for contact scraping, and as a component of applications used for web indexing, web mining and data mining, online price change monitoring and price comparison, product review scraping (to watch the competition), gathering real estate listings, weather data monitoring, website change detection, research, tracking online presence and reputation, web mashup and, web data integration.***

***Web pages are built using text-based mark-up languages (HTML and XHTML), and frequently contain a wealth of useful data in text form.***

## How to scrape websites without getting blocked 

***Web scraping is a task that has to be performed responsibly so that it does not have a detrimental effect on the sites being scraped.***

### Web Scraping best practices to follow to scrape without getting blocked 

* Respect Robots.txt : 

*Web spiders should ideally follow the robot.txt file for a website while scraping. It has specific rules for good behavior such as how frequently you can scrape, which pages allow scraping, and which ones you can’t. Some websites allow Google to scrape their websites, by not allowing any other websites to scrape. This goes against the open nature of the Internet and may not seem fair but the owners of the website are within their rights to resort to such behavior.*

* Make the crawling slower, do not slam the server, treat websites nicely

*Web scraping bots fetch data very fast, but it is easy for a site to detect your scraper as humans cannot browse that fast. The faster you crawl, the worse it is for everyone. If a website gets too many requests than it can handle it might become unresponsive.* 

*Use auto throttling mechanisms which will automatically throttle the crawling speed based on the load on both the spider and the website that you are crawling. Adjust the spider to an optimum crawling speed after a few trials runs. Do this periodically because the environment does change over time.* 

* Do not follow the same crawling pattern 

*Web scraping bots tend to have the same crawling pattern because they are programmed that way unless specified. Sites that have intelligent anti-crawling mechanisms can easily detect spiders by finding patterns in their actions and can lead to web scraping getting blocked.*

*Incorporate some random clicks on the page, mouse movements and random actions that will make a spider look like a human.*

* Make requests through Proxies and rotate them as needed 

*When scraping, your IP address can be seen. A site will know what you are doing and if you are collecting data. They could take data such as – user patterns or experience if they are first time users.*

*Multiple requests coming from the same IP will lead you to get blocked, which is why we need to use multiple addresses. When we send requests from a proxy machine, the target website will not know where the original IP is from, making the detection harder.* 

*There are several methods can be used to change your outgoing IP.*

1. TOR
2. VPNs
3. Free Proxies 

* Use Captcha Solving Services 

*Many websites use anti web scraping measures. If you are scraping a website on a large scale, the website will eventually block you. You will start seeing captcha pages instead of web pages. There are services to get past these restrictions such as 2Captcha or Anticaptcha.*

*If you need to scrape websites that use Captcha, it is better to resort to captcha services. Captcha services are relatively cheap, which is useful when performing large scale scrapes.*

* How can websites detect and block web scraping ?

*Websites can use different mechanisms to detect a scraper/spider from a normal user. Some of these methods are enumerated below:*

1. Unusual traffic/high download rate 
2. Repetitive tasks performed on the website in the same browsing pattern 
3. Checking if you are real browser 
4. Detection through honeypots  
