# Joke-Recommender-System
Two recommendation systems have been built:
1) A simple recommendation system:
    - This is built using the Pearson's correllation coeffecient 
    - Jokes recommended are from the same dataset
2) A more complex recommendation system using collaborative filtering 
    - This is built using collaborative filtering
    - Jokes recommended from another dataset based on user choices on a different initial dataset

Steps taken to implement Simple Recommender System:
1) Cleaning the dataset
    - Interpreting what the data stands for as it only contained numeric values 
    - Renaming the rows and columns with meaningful names
    - There were some garbage values in the dataset like "99" which essentially meant that the joke was not rated by that user (ratings range from -10 to +10)
    - Mean of the column was chosen to replace the garbage value as it would not affect the correlation between two jokes as much.
 
2) Correlation between two jokes: This is calculated using the function shown below which calculates the difference between a value in a column and the mean of the column. This is done for both the jokes to be compared and then correlation between them is calculated using the last line of the function shown in the diagram (Pearson's correlation coeffecient)
![image](https://user-images.githubusercontent.com/79359151/109815105-3efbd080-7c6a-11eb-801b-54f068bdfd0c.png)




The following are included:
1) A jupyter notebook file of type .ipynb containing cleaning of the datasets and building of the recommender system
2) Three excel files containing joke ratings(by several thousand users) for 100 jokes 
3) A folder containing links to all the 100 jokes
4) A powerpoint presentation with a detailed description of the project



