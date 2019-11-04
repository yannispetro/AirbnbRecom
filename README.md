# AirbnbRecom

An Airbnb Listing Recommendation System

Leisure travelers face the problem of choosing the best city location to stay. Even though it is quite simple to identify areas with good transportation connections that are close to the most popular sights, a great trip is highly determined by the degree that the specific “style” of the neighborhood of settlement matches the traveler’s style and preferences. In this regard, I intend to build an effective recommendation system, that will choose Airbnb listings which are located in areas that are ideal with respect to the particular traveler’s profile.

So far, I have utilized Yelp reviews and Airbnb listings description data in the city of Toronto. The traveler’s profile is determined by the provided keywords. Since the “style” of a neighborhood is highly determined by the characteristics of the restaurants, coffee shops, and bars, these types of businesses are extracted from the Yelp Challenge Dataset (it includes data from approx. 15 cities) and a sentiment analysis model is trained first, that provides the possibility of determining whether the business reviews are positive or negative. Next, the business locations that contain the provided keywords in their positive reviews are extracted and constitute the dataset X. In addition to that, Airbnb listings locations that contain the keywords in the neighborhood description are added to X. A Gaussian mixture clustering algorithm is utilized next, to identify the different areas in the city that have a high density of businesses and Airbnb listings that match the traveler’s preferences. 

For the recommendation part, the user selects the type of accommodation (e.g., entire apartment) and maximum budget and all the listings that match those criteria are extracted from the Airbnb dataset. Finally, the recommendation score is calculated as the total probability of the listing’s location with respect to all the identified clusters, weighted by the ratio of the businesses in the respective cluster that contain the keywords in their reviews, over the total number of business in the cluster. The listings with the top N scores are shown to the user. This system yields meaningful recommendations of listings that are not always located in the most “dense” (with respect to the number of restaurants, bars, etc.) central areas, but in areas that reflect the traveler’s preferences determined by the provided keywords.

During the TDI program, I intend to extend this system by two means. First, a model should be built to determine the relevance of the provided keywords to text data, without the text containing the keywords necessarily. At the current point, I only use stemming for that purpose. Second, I would like to utilize more data, such as Instagram posts scraped from the web, that will not only provide significantly more insight about the “style” of particular neighborhoods, but it will reveal the current trends as well. This will highly enhance the quality of the recommendation system.
