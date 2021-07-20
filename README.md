# Robotic-Process-Automation

Process Flow of EASIBOT_Analysis

Get the list of stocks from text file (stockList.txt)
Extract historical stock price through data scrapping from website (e.g. Yahoo Finance) 
Save the extracted data of each stock in Excel spreadsheet (HistoricalData_<companyName>.xlsx)
     under the folder HistoricalData. 
Perform data cleaning on the extracted data
Remove rows that are not number (e.g. with the word “Dividend”)
Remove comma for number (esp volume : 1,458,800)

Compute for other parameters (e.g. x-days moving average)
Create new columns (Vol_20-days_moving avg, Price_20-days_movingAvg, Price Change) 
Analyze each stock from the extracted and computed data
Save analysis in a text file (stockAnalysisResults.txt)
Inform user on the outcome of the analysis via email 


Process Flow of EASIBOT_Execute
Read email periodically until it receive an instruction attachment file (instruction.xlsx)
If no attachment is received, check also the time is before trading session close time. If already pass
      the trading close time, then end the EASIBOT application.
When an instruction file is received save a copy under today date folder for record. 
      (e.g. \Instructions\<Today Date>\instruction.xlsx)

Get the instruction detail from the instruction.xlsx:
  
Company name
Company trading code
Transaction Type (Buy or Sell)
Quantity (number of shares to transact)
Price to transact

Open the trading browser
Login trading account
Search and click on the stock in the browser
Fill the e-trading form [transaction type (buy or sell), price and quantity] and submit
Logout trading account
