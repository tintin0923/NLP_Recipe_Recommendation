# NLP Recipe Recommendation
### Project Overview
##### The Recipe Recommendation System is designed to personalize recipe suggestions to enhance user experience by closely aligning recommendations with individual dietary needs, taste preferences, and time constraints. Using a dataset of 125,000 recipes, this system utilizes natural language processing and machine learning to categorize and recommend recipes that best match user inputs.

### Download and Load the Data
##### Download the JSON file(recipes_raw.zip) from the Google Drive link: https://drive.google.com/drive/folders/13MGNC_5HNMW0KlfKI-F2QSNK2WDaLPwA?usp=sharing
Using data_cleaning_and_preprocessing file for basic data cleaning and preprocessing

### System Development(recipe_recommendation file)
#### ‧ Baseline Model: 
Initially, the text data (titles, ingredients, instructions) from the recipes was vectorized using TF-IDF to transform it into a numerical format. User inputs(text) were similarly vectorized.

#### ‧ Cosine Similarity Calculation: 
The system calculated similarity scores between user input and recipes using cosine similarity. These scores were then weighted and combined to recommend recipes.

####  ‧ Flavor Labeling: 
To enhance the accuracy of recipe recommendations, the system categorizes recipes into 10 distinct flavor profiles, such as sweet, sour, and spicy. This categorization is achieved by identifying specific keywords like sugar, salt, and lime within the titles and instructions of each recipe. Using cosine similarity, the system analyzes these text elements to assign the most relevant flavor profile to each recipe. This method ensures that each recipe is appropriately tagged with a flavor label that reflects its dominant taste characteristics.

####  ‧ Model Training: 
Logistic regression classifiers were developed using flavor-labeled data to predict the user's preferred flavor profile for recommended recipes. This approach enables the system to tailor recipe suggestions based on the user's taste preferences.

####  ‧ Handling Unique Ingredients and Time Constraints: 
Regular expressions and natural language processing (SpaCy) were employed to filter out irrelevant words and extract cooking times, respectively. Significant ingredients were given higher weight in the similarity calculations, and cooking times were standardized to minutes.

### Final Recommendation Calculation:
##### The system initially predicts the user’s preferred flavor profile by employing a logistic regression classifier trained on user interaction data. Following this, it filters the recipe dataset to include only those recipes matching the predicted flavor profile. The recommendation algorithm then computes normalized cosine similarity scores for the recipe titles, ingredients, and cooking times. These scores are weighted and aggregated into a comprehensive final score for each recipe. This calculated score determines the recipe recommendations provided to the user, ensuring that they align precisely with the user’s taste preferences and other input parameters.

### User Interface(recipe_recommendation_user_interface file)
##### At the conclusion of the project, an interactive user interface was developed to facilitate user engagement. This graphical user interface (GUI) allows users to input their specific needs and preferences. Based on these inputs, the system dynamically recommends recipes that best match the user's criteria, providing a tailored and user-friendly experience.
