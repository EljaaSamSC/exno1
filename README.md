# Exno:1
Data Cleaning Process

# AIM
To read the given data and perform data cleaning and save the cleaned data to a file.

# Explanation
Data cleaning is the process of preparing data for analysis by removing or modifying data that is incorrect ,incompleted , irrelevant , duplicated or improperly formatted. Data cleaning is not simply about erasing data ,but rather finding a way to maximize datasets accuracy without necessarily deleting the information.

# Algorithm
STEP 1: Read the given Data

STEP 2: Get the information about the data

STEP 3: Remove the null values from the data

STEP 4: Save the Clean data to the file

STEP 5: Remove outliers using IQR

STEP 6: Use zscore of to remove outliers

# Coding and Output
import pandas as plt

a=plt.read_csv('Data_set.csv')

a

output <img width="1339" height="446" alt="image" src="https://github.com/user-attachments/assets/797ec365-781c-429f-b1cc-d339156f507e" />

df=plt.DataFrame(a)

df

output <img width="1339" height="461" alt="image" src="https://github.com/user-attachments/assets/d662b705-8218-462c-9689-5e58ed2e2749" />

df.info()

output <img width="714" height="352" alt="image" src="https://github.com/user-attachments/assets/3d68666d-9d03-44f2-a9b6-b2efca08e0d9" />

df.describe()

output <img width="1002" height="313" alt="image" src="https://github.com/user-attachments/assets/d4d26011-85f4-4b39-8982-a514a7f8bb3d" />

df.isnull()

output <img width="1314" height="435" alt="image" src="https://github.com/user-attachments/assets/315ec122-2a06-4e33-963f-226de4cef480" />

df.isna().sum()

output <img width="622" height="218" alt="image" src="https://github.com/user-attachments/assets/689ced4d-e597-4320-b473-9a99be84e838" />

df.notna()

output <img width="1324" height="438" alt="image" src="https://github.com/user-attachments/assets/45e3e7b4-e03f-4f0c-b1ff-86ed8ed1fccf" />

df.notna().sum()

output <img width="598" height="220" alt="image" src="https://github.com/user-attachments/assets/9bdcc9dd-2e66-40a5-9cd7-f4fee4a3be58" />

df.duplicated()

output <img width="664" height="275" alt="image" src="https://github.com/user-attachments/assets/c1b9f747-c1ea-4d86-9a68-0c519ff9bb0b" />

[df.duplicated]

output <img width="1325" height="783" alt="image" src="https://github.com/user-attachments/assets/4cd1dd63-7fe5-4378-90df-721cbb74bc50" />

 <img width="1023" height="761" alt="image" src="https://github.com/user-attachments/assets/838e0121-c118-414a-ba26-05c88daafb4c" />

 df.dropna()

output <img width="1369" height="618" alt="image" src="https://github.com/user-attachments/assets/38abef4e-3375-4d33-b4db-5f913be27b2b" />

df.dropna(axis=1)

output <img width="841" height="465" alt="image" src="https://github.com/user-attachments/assets/3a2df07a-0981-4932-b3c2-76e0124f5722" />

df.dropna(axis=0)

output <img width="1361" height="622" alt="image" src="https://github.com/user-attachments/assets/fa0fc78d-fc33-4723-a6ff-5abb70b14f56" />

df.fillna("Weakhero")

output <img width="1357" height="629" alt="image" src="https://github.com/user-attachments/assets/53875b20-9a28-476f-bada-1f5e8f5f9c40" />

df.bfill()

output <img width="1373" height="467" alt="image" src="https://github.com/user-attachments/assets/ac04a34d-90e0-44d3-b02a-060aa1e02cd0" />












# Result
  Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
