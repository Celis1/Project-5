# Using Live Feed to Identify Road Closures

The goal of this project was to use social media and real-time data to identify road closures. In this repo you will find the following:
- [01 - Code for scraping Twitter and returning outcomes](https://github.com/Celis1/Project-5/blob/master/01_scrape_twitter_output.ipynb),
- [02 - Code for scraping FEMA app](https://github.com/Celis1/Project-5/blob/master/02_scrape_fema.ipynb),
- [03 - Code for scraping News API](https://github.com/Celis1/Project-5/blob/master/03_scrape_news_api.ipynb),
- [04 - Sample output from scraping Twitter](https://github.com/Celis1/Project-5/blob/master/04_twitter_output_data.csv)
- [05 - FXN Presentation](https://github.com/Celis1/Project-5/blob/master/05_FNX_final_presentation.pptx).

This project was developed by:
- [Alex Celis], 
- [April Griffin](https://www.linkedin.com/in/april-g-a77b3812b/), 
- [Jamila Holt](https://www.linkedin.com/in/jamilaholt/), and
- [Jordan Nelson](https://www.linkedin.com/in/jordanhowesnelson/)

as part of the Data Science Immersive program with [GeneralAssembly](https://generalassemb.ly) in October 2018.

# Executive Summary

### Intro
Social media is a increasingly relevant source of information due to its quick communication of real-time information. For example, @ArizonaDOT once tweeted “US 89 closure: Because of storm damages, the highway is closed between Cameron and US 160…” This information is essential for emergency personnel during disaster situations because it allows them to work more efficiently and effectively in times of crisis.

### Scraping 
Group FXN was tasked with using social media and real-time data to identify road closures, identify locations of road conditions that would cause drivers to reroute during evacuations or an emergency response, and finally to design the functionality that would allow users (both the public and first responders) to search for a condition. 

Team FXN undertook three separate tasks to accomplish this goal. One important part of this project was data collection.  Data was collected in two different ways: using application programming interfaces to scrape and with traditional web scraping.  Developer accounts were obtained for Twitter's API and News API. Functions were written to allow for semi-automatic scraping of live tweets and news headlines. Traditional web scraping was used to gather data from the Federal Emergency Management Agency Disaster Reporter application.

### Function 
After pulling the data from all these different sources, the main concern is the text from these sources. The data is loaded into Python scripts, and these scripts do 3 main things. First, they define a list of important words. This includes the search terms the user specifies, but also includes some words we’ve defined in the background that the user may not have specified but which would be important to finding road problems. These background words include things like “closed”, “street”, “flood”, “inaccessible”. Part of our efforts to continually improve this project is altering this list of words to be as responsive to road issues as possible. The second step is to extract text features from the data: for Twitter this would be tweets, for NewsAPI this would be headlines, summaries, and sometimes full articles, and for FEMA this would be short descriptions and exact locations.

Finally, we use Python to break these texts down into individual, searchable words, and we compare what is in these texts to the words in our important words list. We count the number of occurrences of important words in a text and assign a score. If a text, for example a tweet, has more of the important words than another text, then it will have a higher score, and higher scored texts will be displayed first to the user. This ensures that the most relevant and urgent results rise to the top. The user can then use the results to find road closures that are important to them, or just identify road closures in general so that they can start rerouting people.

### Demonstration 
An example of how this function works, is as follows. A Twitter user submits a tweet, "#hurricanepython is hitting dc! A tree fell down in the middle of mcpherson sq and is blocking 15th and m! #roadclosed" Emergency service providers would be able to use the search function by inputting keywords that are relevant to their desired outcome. For example, they could search the event keyword (#hurricanepython), relevant geographic location (dc), and intersection or road (15th and M Street) and the condition of concern (road closed). This function would work better than searching these terms on just Twitter because then scrape multiple social media sites (Twitter, FEMA App, global news sites) and would return prioritized output. In the case of the hypothetical Twitter example, the road closure tweet would be ranked highest and returned to the user. Additional information could also be customized to the users desired output: geocoordinates, timestamp, images, and urls.

### Next Steps
There are a number of things that could be done to improve this work. First, increasing the amount of access to Twitter. There are a number of features (including many geo-coordinates) that are not included in the basic-developer access to Twitter. Second, once geo-coordinates are accessible this would be best viewed on a mapping platform, such as Waze. This visualization will allow response vehicles to be quickly rerouted during travel. Lastly, having cross platform validation to increase the validity of the models abilities would greatly increase its ability to make predictions.

### Conclusion
In summary, social media is a valuable tool that can be used to identify road conditions and other valuable information during a natural disaster. Team FXN has shown that data can be collected from Twitter, News API and FEMA and results can be returned in a ranked order to provide valuable information to first responders. Getting real-time relevant information to first responders during an emergency is crucial to rerouting vital services that are crucial during disaster events.


