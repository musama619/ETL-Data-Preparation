# ETL-Data-Preparation

* # Softwares 

![0](https://user-images.githubusercontent.com/34093998/87681669-55ffb800-c798-11ea-9123-c56b16b0cb31.png)
![download (1)](https://user-images.githubusercontent.com/34093998/87681207-d70a7f80-c797-11ea-8f85-e84bba4e1210.jpg)

* Microsoft® SQL Server® 2014 Express (https://www.microsoft.com/en-pk/download/details.aspx?id=42299)
* SSDT-BI (https://www.microsoft.com/en-pk/download/details.aspx?id=42313)


# Project Folders Structure
1. Original Data
2. Prepared Data 
3. Upload Data
4. Analysis

## Steps Performed in Data Preparation

* Copy and Paste data in Prepared Data folder
* Changed Date format
* Changed two same name columns to 'Name' and 'Surname' 
* Now paste the prepared data in Upload Data Folder
* Created new Data Flow in SSIS. Take Flat File Source from Upload Data folder and performed error handling

## Data Flow

![image](https://user-images.githubusercontent.com/34093998/87772672-7fbdeb00-c83b-11ea-9f1e-07d9ec620cf4.png)


1. Flat file source to Conditional Split 1 where it is checked if the data is missing or not. If it is missed then it is moved to Flat file Destination <br>
   in Analysis folder as Insufficiant Data.
2. The data which has passed the condition test is now moved to another Conditional Split where the quality of data is checked.
3. The data which has passed the condition is marked as Good Data and moved in our SQL Server Express Database. The data marked as Bad Data is moved in <br>
   in Analysis folder


## Errors Handled

* Removed empty data fom 'BloodType', 'Kilograms', and 'Centimeters' columns
* Changed Output Columns Width to 1000 to avoid error

# SSIS Errors
* Truncation 
  * Occur when data is duplicated
* Bad Input File Format
* Connection Failure 

