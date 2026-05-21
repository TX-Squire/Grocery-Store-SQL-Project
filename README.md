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

I ran into an error downloading the data as the size of the value item_code is 15 digits long. I discovered using the "DESCRIBE" SQL command that Excel labeled the value as and int whos largest value is 32bits. I converted the column into a BIGINT. I have to convert a column's data type in all four intput files which took a pretty long time as I had to rerun the program four times to make it happen. According to Gemini, typically numbers above 15 digits in Excel should be formatted as text to avoid truncation. In the future I could have converted the culumns as text in Excel and then converted them to BIGINT in MySQL.

<img width="735" height="283" alt="image" src="https://github.com/user-attachments/assets/445f489b-b23f-439f-b020-c345cecc03bc" />

Running the Python code csv_to_sql.py took under a minute.

# Analyzing the Data

Looking at the the data files, it is unclear what information they hold. I''l examine them one by one.

# Annex1
<img width="485" height="191" alt="image" src="https://github.com/user-attachments/assets/9e6c9a2c-422d-4e8f-93dd-2e8adbfa6b0c" />
This file essetially catagorizes teh items.

#Annex2
<img width="753" height="227" alt="image" src="https://github.com/user-attachments/assets/66e38168-3f1f-4301-bd6e-e23ae300a1c7" />
This file contains a timeline of the items sold.

# Annex3
<img width="345" height="259" alt="image" src="https://github.com/user-attachments/assets/4582c4f0-81b4-4d72-96ee-2da422a56ae5" />
This file links items to price.

# Annex4
<img width="359" height="291" alt="image" src="https://github.com/user-attachments/assets/cef2522e-9451-412f-9679-5f20a8cd1bcf" />
This file pairs an item to a loss rate.

<img width="581" height="157" alt="image" src="https://github.com/user-attachments/assets/4e933483-be72-4995-9e88-95cdddabb44c" />

For practice, I will now answer some common questions I might get about the data.

First, let's count the number of items sold in 2021. I looked up all the instances of the year 2021 in the file and found the following result:
<img width="449" height="291" alt="image" src="https://github.com/user-attachments/assets/35383173-5d7b-439a-8327-e6136ae14f97" />

This is the answer to this question. I first ran into an issue with this question because apparently when you upload the same data into SQL it combines it to the data already there. Consequently, I had way too many data values. I had to delete the database and start again. Then I ran into a different issue where the value of Item_Code did not have enough significant digits because Excel was transforming it into a Scientific data type with three sig-figs. The way I overcame this issue is by creating a new column in the file called Item_Code_Text which added an apostophe to the beginning of each number so that Excel would automatically convert it into text. This solution worked.
<img width="181" height="102" alt="image" src="https://github.com/user-attachments/assets/5b5950c8-816f-4246-9ebc-318532047f15" />

There are 243 distinct items in the data:
<img width="602" height="445" alt="image" src="https://github.com/user-attachments/assets/96f60ae3-9638-4e54-9a80-c29ad6c94563" />

