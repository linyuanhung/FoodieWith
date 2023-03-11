# FoodieWith
For foodies with dietary restrictions, it is difficult to find restaurants with tasty food that accommodate dietary restrictions. It is even more difficult when searching for a restaurant that can accommodate a party with multiple dietary restrictions. FoodieWith is a website that addresses this problem by making restaurant recommendations based on user input such as dietary restrictions, location, and other preferences.

## Demo
Currently live for Philadelphia restaurants:
https://linyuanhung-foodiewith-app-xzjstp.streamlit.app/

## Site

### Users input their preferences

FoodieWith then provides the top ten restaurants based on user preference. The user can select from most reviewed, best for each dietary restriction, and distance.


<img width="617" alt="Screenshot 2023-03-10 at 6 48 43 PM" src="https://user-images.githubusercontent.com/104601250/224461095-7cc453db-0d0b-4d78-9c59-febd92fad40e.png">

### Restaurant map

<img width="833" alt="Screenshot 2023-03-10 at 6 48 52 PM" src="https://user-images.githubusercontent.com/104601250/224461101-18a08cf1-a458-47e2-b725-eded7e1c409f.png">

FoodieWith then provides a map with a numbered blue icon to show the ranking and location of the top ten restaurants as well as a red icon for the user location. The user can hover over the numbered icon to get the restaurant name.

### Restaurant info

<img width="1090" alt="Screenshot 2023-03-10 at 6 49 19 PM" src="https://user-images.githubusercontent.com/104601250/224461140-9bd1fb58-f851-4b87-bc2d-6c2c33ba21ef.png">

To learn more about their choices, the user can open the next tab, which lists out the restaurants by their rankings and displays the restaurant category. 

<img width="1102" alt="Screenshot 2023-03-10 at 6 49 33 PM" src="https://user-images.githubusercontent.com/104601250/224461145-011850a7-6e83-4e1d-9df5-54d8464f3a9f.png">

The user can click the down arrow to expand this box and see the overall ranking and the ranking for each dietary restriction. The rating distribution for each dietary restriction is also displayed as a horizontal histogram for the user. 

<img width="1034" alt="Screenshot 2023-03-10 at 6 49 48 PM" src="https://user-images.githubusercontent.com/104601250/224461160-79cb0b25-a1e6-4909-ae7c-56160602ad6f.png">

The most recent and useful reviews for each dietary restriction are also displayed to help the user decide on where to go for dinner.

## Why
In my family, my sister is vegetarian and I have a gluten allergy. Deciding on a restaurant for dinner is often a long and involved process. We would all have our phones out to cross check menus and Yelp reviews to find a restaurant that is both tasty and can accommodate our dietary restrictions. This problem is also not specific to my family--40% of Americans have a dietary restriction due to preference, religion, or health conditions (Statistica, 2021). 

FoodieWith streamlines the process of finding a tasty restaurant that can accommodate everyone’s dietary preferences by providing one centralized website where the user can enter their party’s dietary preference(s) and get a list of nearby and open restaurants that can accommodate everyone.

## How
FoodieWith uses Yelp’s dataset to recommend tasty restaurants in Philadelphia based on the user preferences. The user can input their dietary restriction(s), their zip code (currently only for Philadelphia), how many miles they are willing to travel, date and time that the user will be dining, and their restaurant ranking preference. 

### FoodieWith pipeline

![230213_diagram3](https://user-images.githubusercontent.com/104601250/224460245-dad1f0e2-1b00-4027-bf92-2ce46751563f.png)

FoodieWith recommends only tasty restaurants (at least 4 star average) that accommodate the user's dietary restriction(s) (at least 4 star average).

FoodieWith searches Yelp reviews

![230214-diagram](https://user-images.githubusercontent.com/104601250/224460340-302614e2-71a5-4925-b17c-e723a75e939e.png)


FoodieWith then goes through reviews from good restaurants (with at least a four star overall rating) in Philadelphia to identify nearby restaurants and pull out reviews with keywords associated with the dietary restriction(s) of interest. For example, FoodWith searches for "celiac" and "gluten-free" to identify reviews from gluten-free diners.

FoodieWith analyzes reviews and reccomends restaurants
![230214-diagram1](https://user-images.githubusercontent.com/104601250/224460370-e2a5c17c-444f-4ff2-8e15-51fbbed732fa.png)

For example, FoodieWith counts the total number of reviews from gluten-free diners and averages the star rating of these reviews. Only restaurants with at least a 4 star average rating for your dietary restriction(s) are recommended.

FoodieWith shares relevant reviews

![230214-diagram2](https://user-images.githubusercontent.com/104601250/224460420-2f4a995d-bd6f-4975-9ad7-bc50270bf70b.png)
FoodWith displays the most recent and useful reviews that mention your dietary restriction(s).

## Built with
Python, Streamlit

## Next steps
1. add other restaurant features (ex: takes reservations)
2. expand to other cities
3. webscrap for restaurant reviews
