# Joke-Recommender-System
Two recommendation systems have been built:
1) A Simple Recommendation system:
    - This is built using the Pearson's correllation coeffecient 
    - Jokes recommended are from the same dataset
2) A more Complex Recommender system:
    - User-to-User Recommender system using cosine similarity
    - User-to-User Collaborative Filtering


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


### **Correlation heatmap comparing every suggested joke with each other**
![image](https://user-images.githubusercontent.com/79359151/109818830-63f24280-7c6e-11eb-89b3-8ddfc156fa32.png)

### Observations:
   - As well as this system works, it is still a very simple recommender system. Having to recommend jokes to the user based on a SINGLE joke that the user likes, might not be that accurate. So if the user provides more jokes that he/she likes, then the suggestions can be better informed ones.
   - For this example, let us assume that the user likes Joke 5 as well. The process followed to tackle this:
   - Find the top 30 most correlated jokes with respect to Joke 1. 
\
\
![image](https://user-images.githubusercontent.com/79359151/109819315-e418a800-7c6e-11eb-9c05-9c6097b43abd.png)

   - Finding the jokes that are common to both lists help provide a better informed recommendation of jokes


![image](https://user-images.githubusercontent.com/79359151/109820142-b2eca780-7c6f-11eb-82ba-e0af0b0b3234.png)





## **User-to-User Recommender System**
![image](https://user-images.githubusercontent.com/79359151/109822036-8c2f7080-7c71-11eb-8d85-eb92527a2b2d.png)
### 1) Prepare dataset "jester-joke-2" as a test set 
\
![image](https://user-images.githubusercontent.com/79359151/109822276-c4cf4a00-7c71-11eb-98be-180b6678881e.png)
### 2) Extract a single user record and also keep the top 10 liked jokes of that user
![image](https://user-images.githubusercontent.com/79359151/109822498-f7794280-7c71-11eb-8f4e-95a253518ae6.png)
### 3) Append the user record to jester-joke-1 data frame and replace the NaN's with the mean values of the corresponding column
![image](https://user-images.githubusercontent.com/79359151/109822723-30b1b280-7c72-11eb-8441-b739ec640e1b.png)
### 4) Cosine similarity between users and transfer to absolute values
![image](https://user-images.githubusercontent.com/79359151/109822828-4c1cbd80-7c72-11eb-8692-01ee0a7d13b0.png)
### 5) Get the top 100 similar users and their ratings
![image](https://user-images.githubusercontent.com/79359151/109822888-5c349d00-7c72-11eb-8823-bf7859f4105b.png)
### 6) Recommend 20 jokes based on similar users
![image](https://user-images.githubusercontent.com/79359151/109822989-766e7b00-7c72-11eb-8ff4-e03fff90f6e2.png)



## User-to-User Collaborative Filtering
![image](https://user-images.githubusercontent.com/79359151/109823987-60ad8580-7c73-11eb-98f0-235cafc818e4.png)
### 1) Starting with "jester-joke-1"
![image](https://user-images.githubusercontent.com/79359151/109824153-85096200-7c73-11eb-9260-6bf045ee4462.png)
### 2) Reshape the dataframe and store it as a new dataframe
![image](https://user-images.githubusercontent.com/79359151/109824356-b6822d80-7c73-11eb-8a42-ab51ce225d00.png)
### 3) train_test_split: train:test = 3:1 (random 75%)
![image](https://user-images.githubusercontent.com/79359151/109824699-06f98b00-7c74-11eb-908c-a4627d7fd4d6.png)

### Now the collaborative filtering can be done in two ways:
### 1) By Mean: 
![image](https://user-images.githubusercontent.com/79359151/109824915-41632800-7c74-11eb-9cc1-4746b8c637f7.png)
### 2) By Weighted Mean: 
   - Cosine similarity as the weight
   ![image](https://user-images.githubusercontent.com/79359151/109825044-635caa80-7c74-11eb-8aa1-67750d460622.png)
   - using weighted mean ratings \
   ![image](https://user-images.githubusercontent.com/79359151/109825130-7a030180-7c74-11eb-8d22-7a55d0528bf7.png)


## Visualizations by User
![image](https://user-images.githubusercontent.com/79359151/109825273-a028a180-7c74-11eb-872d-6e78c6b6bf1e.png)
![image](https://user-images.githubusercontent.com/79359151/109825308-aae33680-7c74-11eb-9950-6fdaf1bfd142.png)
![image](https://user-images.githubusercontent.com/79359151/109825360-b6cef880-7c74-11eb-96f3-7c62ee41c8ed.png)

## Visualizations by Joke
![image](https://user-images.githubusercontent.com/79359151/109825435-c9e1c880-7c74-11eb-9112-be37eeb62531.png)
![image](https://user-images.githubusercontent.com/79359151/109825527-de25c580-7c74-11eb-8c96-356209615df7.png)

The following are included:
1) A jupyter notebook file of type .ipynb containing cleaning of the datasets and building of the recommender system
2) Three excel files containing joke ratings(by several thousand users) for 100 jokes 
3) A folder containing links to all the 100 jokes
4) A powerpoint presentation with a detailed description of the project



