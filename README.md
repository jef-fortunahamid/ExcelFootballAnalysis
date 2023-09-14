## Excel Football Transfer Analysis

### Case Description
This project was done through 365DataScience Unguided Project. Here's the [Project File](https://docs.google.com/spreadsheets/d/19dw1WeoOEQqihduN2XaSYan1zNHBUBKY/edit?usp=drive_link&ouid=116937846114956243807&rtpof=true&sd=true)

Here's the Final ouput, [Football Transfer Analysis](https://docs.google.com/spreadsheets/d/1MgM5m-jTrqR1MyM3enYtkMLbyo0NVDvx/edit?usp=drive_link&ouid=116937846114956243807&rtpof=true&sd=true)

*This Football Transfers Analysis in Excel project involves extensive data analysis of the intricacies and economic patterns within international football (‘soccer’ in the US) transfers. It delves into the movement of players from one association to another, offering an in-depth overview of the economics of international football.*

*Using a robust football dataset spanning two seasons (2021/2022 and 2022/2023), the analyst is asked to perform several key tasks in Excel—including data preprocessing and manipulation, filtering, working with Excel functions proficiently, and data visualization.*

*Students working on this project will map transfers to and from countries across different associations, create summary tables to illustrate these transfers, compute net transfer movements, and obtain the total dollar amounts for the respective transactions.*

*This Excel project offers a unique opportunity to blend the passion for football with the excitement of data-driven insights, fostering a deeper understanding of the global football economy. Whether you're a football enthusiast, a data analysis student, or both, this Excel project promises intriguing findings and a new perspective on this captivating game. It’s the perfect opportunity to validate several essential Excel skills you learned in the Introduction to Excel course.* (Excerpt from the course)

### Techniques Used:
- **Text to Columns**: Using the 'Data' tab, the country and continent information is separated using a comma as the delimiter.
- **TRIM Function**: Used to remove the extra space before the continent names.
- Copy-Paste Special and Add Filter: The cleaned-up data is pasted back, and filters are applied to each column.
- Formatting and Filters: Headers are formatted, and filters are applied to each column.
- Find/Replace: Used to correct erroneous values in the 'Season' column.
- INDEX/MATCH Functions: Used to fill missing 'Continent' information based on the 'Countries' sheet.
- Formatting Cells: The 'Total club to club compensation' column is formatted to display values in a uniform manner.

### Part 1: Data Exploration and Preparation
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

We need to change the value with Find/Replace Function (press CTRL + H). On the 'Find what' space, type '2022/2028' and on 'Replace what' space, type 2022/2023, and press 'Replace All'.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/10870d37-e295-4424-a1a9-d14875b37cae)

Now it is sorted.

<img width="206" alt="image" src="https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/a13d7310-7e52-441a-8849-75db4b23a65c">

Next, we need to fill out the missing values on the two columns for the named 'Continent'. We will be using INDEX/MATCH functions and the formula is:
```excel
=INDEX(Countries!$C$3:$C$140,MATCH(C4,Countries!$B$3:$B$140,0))
```
And this is the final output for the 'Continent' columns.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/d9c2da3c-48fe-47ec-bdcb-4a57754c6dbb)

The final column to fix is the 'Total club to club compensation'.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/0246c956-666a-4afc-8856-28309a26e5e2)

Looking at the column, the values are not properly shown. The decimal places are not consistent as well. We need to fix this with 'Format Cells' (press CTRL + 1). Select all the values on the column 'Total club to club compensation' (CTRL + SHIFT + DOWN ARROW). On 'Format Cells' choose the 'Custom' function, then type '$#,##0.00;;-'.
- "$#,##0.00": This is for positive numbers. It rounds the number to two decimal places and adds a dollar sign.
- The section for negative numbers is left blank since you mentioned there are no negative values.
- "-": This is for zeros, which will be displayed as a dash.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/a0cd0bc7-c697-40a7-815c-5b5b3b0735a6)

We are now ready for the analysis.

### Part 2: Analysis on the Number of European Transfers
Problem:
*Create a table showing the total number of football transfers in and out of Europe during the two seasons under examination. We're interested in the net transfer balance. Does Europe, overall, import or export more players?*

We have to create columns named as 'Season', 'Transfers Into Europe', 'Transfers out of Europe' and 'Net Transfer Balance'.

On the 'Season' column, we will use UNIQUE formaula to get the values ffrom the 'Season' column on the 'Database' sheet.
```excel
=UNIQUE(Database!$B$4:$B$3352)
```
We need to copy and special paste the values (ALT + E + S + V) on the same rows.

To fill out the values for columns 'Transfers Into Europe' and 'Transfers out of Europe', we will be using the SUMIFS formula.
Transfers Into Europe formula
```excel
=SUMIFS(Database!$G:$G,Database!D:D,"Europe",Database!$B:$B,'Transfers Into & Out of Europe'!$B4)
```
Transfers Out of Europe formula
```excel
=SUMIFS(Database!$G:$G,Database!$F:$F,"Europe",Database!$B:$B,'Transfers Into & Out of Europe'!$B4)
```

This is the final output:
![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/bdf3613c-ea7e-4d7a-ad4b-98552f5c0bd1)

### Part 3: Analysis on European Transfers by Country
Problem:
*Create another table listing the net transfer movements for each European country during the 2021/2022 and 2022/2023 seasons. Include the number of transfers and the total cost, giving you a clearer picture of how money moves around in European football transfers.*

For this problem, the columns that we need to create are:
- Season
- Country
- Transfers Into Country
- Cost of Transfers Into Country
- Transfers Out of Country
- Cost of Transfers Out of Country
- Net Transfers
- Net Cost

On the 'Country' column, we will use UNIQUE and FILTER formulas to get the European Countries from the 'Countries' sheet with the formula:
```excel
=UNIQUE(FILTER(Countries!$B:$B,Countries!$C:$C="Europe"))
```
Then we copy and special paste the values (ALT + E + S + V) on the same rows.

Next, for the 'Transfers Into Country' and 'Cost of Transfers Into Country', we will use the SUMIFS formula:
```excel
=SUMIFS(Database!$G:$G,Database!$C:$C,'European Transfers by Country'!$C4,Database!$B:$B,'European Transfers by Country'!$B4)
```

```excel
=SUMIFS(Database!$H:$H,Database!$C:$C,'European Transfers by Country'!$C4,Database!$B:$B,'European Transfers by Country'!$B4)
```

We did use the same formulas for the next two columns 'Transfers Out of Country' & 'Cost of Transfers Out of Country' with the corresponding 'Database' columns for the Outgoing.

For the columns, 'Cost of Transfers Into Country' and 'Cost of Transfers Out of Country', we need to change the format to properly show the values. Select all the values on each column (CTRL + SHIFT + DOWN ARROW). Press CTRL + 1, on 'Format Cells' choose the 'Custom' function, then type '$#,##0.00;;-'.
- "$#,##0.00": This is for positive numbers. It rounds the number to two decimal places and adds a dollar sign.
- The section for negative numbers is left blank since you mentioned there are no negative values.
- "-": This is for zeros, which will be displayed as a dash.

Then we need to calculate for the 'Net Transfers' and 'Net Cost' columns.
Net Transfers = 'Transfers Into Country' - 'Transfers Out of Country'
Net Cost = 'Cost of Transfers Into Country' - 'Cost of Transfers Out of Country'

For these columns,we need to change the format to properly show the values. Select all the values on each column (CTRL + SHIFT + DOWN ARROW). Press CTRL + 1, on 'Format Cells' choose the 'Custom' function, then type '#;[Red](#)' and '$#,##0.00;[Red]($#,##0.00);-', respectively. On these columns, we made the negatice values in red and in parentheses.

This is the final output:
![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/c6f3fd4e-d2a5-4f22-ab5c-4efaa815ea2a)

### Part 4: Visualise Transfer Fees of Top 5 European Countries
Problem:
*Identify the top five European countries that invested the most in incoming transfers in the 2022/2023 season. For these countries, create a graphic showing the number of players they brought in and the average transfer fee spent per player.*

For these problem, we need to use our European Transfers by Country table and do some filtering. 
First, we need to filter the season to 2022/2023.
The next step is to filter 'Cost of Transfer into Country' column to get the top 5 highest values.

<img width="211" alt="image" src="https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/e221b6d4-701d-4b23-84e1-784dcab97678">

Looking at the filtering option, the values are in increasing order, so the last five values are the top 5 highest values, We just need to select the highest 5 values.

<img width="211" alt="image" src="https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/49d9d634-102e-40a8-be13-53aeb0915d83">

So this is our top 5 countries:
![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/b51d631c-dda2-4a4d-ade0-6c849702ce63)

We will copy the 'Country', 'Transfers Into Country', and 'Cost of Transfer into Country' onto a new sheet.

We need to calculate the Average Transfer Fee per Player and this will be our new column, with the following formula:
Average Transfer Fee per Player = 'Cost of Transfer into Country'/'Transfers Into Country'

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/7a302335-ce51-411c-a549-9c7e53b759ca)

Finally we need to build a dual axis chart. Select the 'Country', 'Transfers Into Country', and 'Average Transfer Fee per Player' columns and click the 'INSERT' tab. ON the 'CHART', choose the 'COMBO' chart with the second option ' Clustered Column - Line on Second Axis'. This is the final output.

![image](https://github.com/jef-fortunahamid/ExcelFootballAnalysis/assets/125134025/c3acc744-9586-4650-bf24-ec17301bea1e)
