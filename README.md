# Grocery Store SQL Project

# inputting data into SQL
In this project I use SQL and python to analyze sales data from a csv file. I aquired the data from this project from a user in the site Kaggle.com which is an excellent site for amatuer data anylist enthusiets. The users nate is YapWH; this user is pretty active and has posted many datasets, also the usablity score given by kaggle is 10/10. The location to the data set is as follows:  https://www.kaggle.com/datasets/yapwh1208/supermarket-sales-data/data.

<img width="1919" height="934" alt="image" src="https://github.com/user-attachments/assets/52f5dcc1-ac63-42b3-9129-43c4bcfa65f0" />

I downloaded the data as a csv file. Now file to upload it into SQL.

I recently watched a useful video on how to do a similar project, but using different data (the video is in Hindi, so I used subtitles).  The url is here: https://www.youtube.com/watch?v=hK-qUy3UfT8&t=511s. I find that learning something new happens in stages: first, you understand the subject by watching someone else do the task, then you learn how to do it on your own, and finally, you may become so proficient that you contribute something new to the subject. I am currently on the second step.

I used the code csv_to_sql.py to transfer the data into MySQL. The code reads the csv files, tranfers them to a Pandas dataframe, and them moves them to SQL.

<img width="1259" height="909" alt="image" src="https://github.com/user-attachments/assets/fe2b2a4e-46a7-484e-b441-435f2916ecdf" />

Meanwhile I created a database in MySQL:

<img width="639" height="262" alt="image" src="https://github.com/user-attachments/assets/8f1090b2-6c83-45e3-b8ac-a2686d17d73a" />

I ran into an error downloading the data as the size of the value item code is 15 digits long. I discovered using the "DESCRIBE" SQL command that Excel labeled the value as and int whos largest value is 32bits. I converted the column into a BigInt:

<img width="735" height="283" alt="image" src="https://github.com/user-attachments/assets/445f489b-b23f-439f-b020-c345cecc03bc" />

