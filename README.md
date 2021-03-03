# Joke-Recommender-System
Two recommendation systems have been built:
1) A Simple Recommendation system:
    - This is built using the Pearson's correllation coeffecient 
    - Jokes recommended are from the same dataset
2) User-to-User Recommender system
2) User-to-User Collaborative Filtering


## **Simple Recommender System:**
### 1) Cleaning the dataset:
    - Interpreting what the data stands for as it only contained numeric values 
    - Renaming the rows and columns with meaningful names
    - There were some garbage values in the dataset like "99" which essentially meant that the joke was not rated by that user (ratings range from -10 to +10)
    - Mean of the column was chosen to replace the garbage value as it would not affect the correlation between two jokes as much.

![image](https://user-images.githubusercontent.com/79359151/109817334-cba78e00-7c6c-11eb-9d75-0a88070ef1b9.png)
![image](https://user-images.githubusercontent.com/79359151/109817415-dfeb8b00-7c6c-11eb-95be-cf2209415f52.png)

 
### 2) Correlation between two jokes: 
   - This is calculated using the function shown below which calculates the difference between a value in a column and the mean of the column. This is done for both the jokes to be compared and then correlation between them is calculated using the last line of the function shown in the diagram (Pearson's correlation coeffecient)
![image](https://user-images.githubusercontent.com/79359151/109815105-3efbd080-7c6a-11eb-801b-54f068bdfd0c.png)

### 3) Building the simple recommender:
   - To manually check the correlation of one joke with every other joke in the dataset would be time-consuming and inefficient. The function below helps to automate this and speed things up.
![image](https://user-images.githubusercontent.com/79359151/109818269-c72fa500-7c6d-11eb-95c6-53dd412a13a5.png)
![image](https://user-images.githubusercontent.com/79359151/109818673-35746780-7c6e-11eb-837a-5eaf98c5b8b3.png)
![image](https://user-images.githubusercontent.com/79359151/109818728-47560a80-7c6e-11eb-8f6b-51c8ed155936.png)
\

\
### **Correlation heatmap comparing every suggested joke with each other**
\
\
![image](https://user-images.githubusercontent.com/79359151/109818830-63f24280-7c6e-11eb-89b3-8ddfc156fa32.png)

### Observations:
   - As well as this system works, it is still a very simple recommender system. Having to recommend jokes to the user based on a SINGLE joke that the user likes, might not be that accurate. So if the user provides more jokes that he/she likes, then the suggestions can be better informed ones.
   - For this example, let us assume that the user likes Joke 5 as well. The process followed to tackle this:
   - Find the top 30 most correlated jokes with respect to Joke 1. 
\
\
![image](https://user-images.githubusercontent.com/79359151/109819315-e418a800-7c6e-11eb-9c05-9c6097b43abd.png)

   - Finding the jokes that are common to both lists help provide a better informed recommendation of jokes
\ 
\
![image](https://user-images.githubusercontent.com/79359151/109820142-b2eca780-7c6f-11eb-82ba-e0af0b0b3234.png)




The following are included:
1) A jupyter notebook file of type .ipynb containing cleaning of the datasets and building of the recommender system
2) Three excel files containing joke ratings(by several thousand users) for 100 jokes 
3) A folder containing links to all the 100 jokes
4) A powerpoint presentation with a detailed description of the project



