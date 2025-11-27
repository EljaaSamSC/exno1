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

df.ffill()

output <img width="1353" height="447" alt="image" src="https://github.com/user-attachments/assets/f1e124f1-3fe3-420f-a580-dcf720487bbf" />

df.bfill()

output <img width="1373" height="467" alt="image" src="https://github.com/user-attachments/assets/ac04a34d-90e0-44d3-b02a-060aa1e02cd0" />

Remove outliers using IQR method

ir=pd.read_csv('iris.csv') 
ir

output <img width="947" height="462" alt="image" src="https://github.com/user-attachments/assets/9fe7828a-ce41-4621-ba2a-f39d6d20a4a9" />

sns.boxplot(ir)

output <img width="1263" height="562" alt="image" src="https://github.com/user-attachments/assets/0a1e0a74-47dc-4781-854a-bdea82ed4b1b" />

sns.scatterplot(ir)

output <img width="1217" height="590" alt="image" src="https://github.com/user-attachments/assets/f04b5edd-8e30-4bb9-afd1-9dbd4e2b4a09" />

q1=ir.sepal_width.quantile(0.25) 
q3=ir.sepal_width.quantile(0.75) 
iqr=q3-q1 
print(iqr)

output <img width="705" height="65" alt="image" src="https://github.com/user-attachments/assets/7721901c-4f8e-4b55-b46f-f8d3c9e625c3" />


rid=ir[((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))] 
rid['sepal_width'] 

output <img width="579" height="116" alt="image" src="https://github.com/user-attachments/assets/9dc699a5-bd10-46f6-a1ae-d70f01576f29" />

delid=ir[~((ir.sepal_width<(q1-1.5*iqr))|(ir.sepal_width>(q3+1.5*iqr)))] 
delid

output <img width="979" height="464" alt="image" src="https://github.com/user-attachments/assets/280119df-9e57-4b6c-bef8-b49335678129" />


Remove outliers using Z-score method

data=[1,12,15,18,21,24,27,30,33,36,39,42,45,48,51,54,57,60,63,66,69,72,75,78,81,
 84,87,90,93] 
df=pd.DataFrame(data) 
mean=np.mean(data)
mean

output <img width="856" height="15" alt="image" src="https://github.com/user-attachments/assets/453f620b-bb6f-41ef-8cb1-c8d4ac67bd95" />

std=np.std(data) 
std 

output <img width="859" height="36" alt="image" src="https://github.com/user-attachments/assets/a750e3e7-4094-4c4f-b2e6-174646000640" />

z=np.abs(stats.zscore(df)) 
z 

output <img width="555" height="770" alt="image" src="https://github.com/user-attachments/assets/3c7a8526-562a-4911-8fa6-0cead3636a0a" />
       <img width="532" height="182" alt="image" src="https://github.com/user-attachments/assets/d30f254c-2961-4ebe-ac20-9e94d353226c" />

threshold=3 
outliers = df[abs(df) > 3] 
print("Outliers:") 
print(outliers) 

output <img width="880" height="682" alt="image" src="https://github.com/user-attachments/assets/5e8654d8-c178-4213-8689-9db6ff4f41d7" />

df_cleaned = df[(z <= threshold)] 
df_cleaned 

output <img width="961" height="775" alt="image" src="https://github.com/user-attachments/assets/b1b337c3-740d-49f8-97c3-fc6161f01d90" />
       <img width="724" height="201" alt="image" src="https://github.com/user-attachments/assets/d1105af5-99fd-488a-b807-1edb9664ac0d" />


# Result
  Thus we have cleaned the data and removed the outliers by detection using IQR and Z-score method.
