# Indian-MF
Data about MF in India

There is dearth of structured data for Indian Mututal Funds online. All financial websites such as Economic Times, Money Control provide information about all MF. But there are no free APIs or datasets available which can be used to directly download all historical data of the NAVs. Both Google Finance and Yahoo Finance APIs do bot provide complete data for Indian MF. The factual data about the MF such as fund size, sector allocation, etc. is also not available in the structured format.

This repository is an attempt towards creating structured, reusable data for Indian MF. People are welcome to improve on this attempt and the ultimate target is to create proper API. There are currently 2 scripts- one for NAVs and other for factual data.

The first file contains Python script for getting NAV (Net Asset Value) data for all mutual funds in India. This data is directly from AMFI (Association of Mutual Funds in India) website, which has searchable option of getting data for a particular mututal fund for a particular time period. 

The first part of the Python script scrapes AMFI site to get the NAV data for all mutual funds in India for a period from 2012 to date (29th Sep, 2018). These dates can be easily modified to change the scope. The script then creates a dataframe with mutual funds along x axis and dates along y axis. Once all the past data is completely scraped, it can be updated daily with the second part of the script, which scrapes daily NAV data from AMFI website and appends it to the past data. This saves effort in getting the entire data every day once the past database is stored. Last section of the script adds useful columns such as the return over past week/month/quarter/year. However, this section needs to be improved as it fails when the past data is missing due to weekend/holiday etc.

The second file scrapes the information from Money Control site, as the official source, AMFI does not provide the necessary data. Updating this data from an official source, if available, is recommended. This data contains key information such as asset size, launch date, fund family, benchmark, fund manager, % holdings by sector and stock. This data is then joined with NAV data to get useful information which can be used for analyzing Indian mutual funds.
