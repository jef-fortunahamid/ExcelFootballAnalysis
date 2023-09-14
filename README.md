## Excel Football Transfer Analysis

### Case Description
This project was done through 365DataScience Unguided Project. Here's the [Project File](https://docs.google.com/spreadsheets/d/19dw1WeoOEQqihduN2XaSYan1zNHBUBKY/edit?usp=drive_link&ouid=116937846114956243807&rtpof=true&sd=true)

This Football Transfers Analysis in Excel project involves extensive data analysis of the intricacies and economic patterns within international football (‘soccer’ in the US) transfers. It delves into the movement of players from one association to another, offering an in-depth overview of the economics of international football.

Using a robust football dataset spanning two seasons (2021/2022 and 2022/2023), the analyst is asked to perform several key tasks in Excel—including data preprocessing and manipulation, filtering, working with Excel functions proficiently, and data visualization.

Students working on this project will map transfers to and from countries across different associations, create summary tables to illustrate these transfers, compute net transfer movements, and obtain the total dollar amounts for the respective transactions.

This Excel project offers a unique opportunity to blend the passion for football with the excitement of data-driven insights, fostering a deeper understanding of the global football economy. Whether you're a football enthusiast, a data analysis student, or both, this Excel project promises intriguing findings and a new perspective on this captivating game. It’s the perfect opportunity to validate several essential Excel skills you learned in the Introduction to Excel course.

### Data Exploration and Preparation
This file has two working sheets named 'Database' and 'Countries'. These are the following steps done.

Database Sheet
![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/93443aaf-45a3-45e6-805f-9acdd9776a7e)

Countries Sheet
![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/f66f79d2-7913-4b3f-9b13-80da887c375a)

Looking at the two sheets, there are few things we need to do to clean up the sheets. 

First, let's focus on the 'Countries' sheet. 
The "Countries" sheet appears to contain information about countries along with their respective continents, formatted as "Country, Continent". We will seperate the country from the continent using the 'Text to Columns' from the 'Data' tab. We will be using the 'comma' as the delimiter. Select the data with CTRL + SHIFT + DOWN ARROW.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/a3586f18-44f9-401d-9b7a-20b4b70fdb1e)

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/cf671f80-5980-48c8-a177-7bf31317b749)

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/de9ffb38-336a-4cad-86db-accdfb596dc0)

Looking at the Continent column there is a space before the continent name. To get rid of it, we'll use the TRIM function.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/4f63b55b-d90a-4b1c-9c09-2200e414d34d)

We Copy and Paste the values on to the Continent column. ALT + E + S + V to special paste values and ALT + A + T to add filter on each column.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/e9396edc-50e4-45df-8362-d87f4ce20a11)

Now, let's turn our attention on the Database sheet. We need to format the header of each of the column and add filter (ALT + A + T), so we can check the values in each column and if there are missing values. 

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/555c7a51-6d3e-4bae-b763-66c2dac6ba61)

We will check the  values in each column.
On Season column, we've got a problem, we've got 2022/2028 instead of 2022/2023.

<img width="212" alt="image" src="https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/598a6fb2-2030-4778-8b1d-b65648c97a71">

