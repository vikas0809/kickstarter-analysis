# Kickstarting with Excel
Performing analysis on Louise Kickstarter to uncover various trends
## Overview of Project

This project performs the data and visual analysis of a crowdfunding project run by up-and-coming playwright, Louise. With a very limited budget of $10,000, she is hesitant about her first fundraising campaign. So, we are helping her to crunch some number and visualize the various trends which help Louise to make her very important decisions to make her campaign successful.

She ran in total of 4114 campaigns in 21 different countries. The response was amazing, she had very successful campaign with total of 2185 campaign. There were some unsuccessful campaigns which were 1530 in total. United States is the country where she ran her most of campaigns.

The main analysis tool we used is Microsoft Excel. Excel is a powerful tool to perform wide range of data visualization operations.

By the end of this project, we will see various trends and key factors which are visualized by various bar-charts, line-charts and pivot tables to analyze the campaign.

## Analysis and Challenges

### Basic structure 
The overview of the dataset is very boring and unorgainzed.We performed some basic formatting steps to make the tabular data look more presentable and easy to read.
- The first operation we performed was to auto-adjust width and height of the cells to make the data fit in the cell and easily readable.

![autofill](https://github.com/vikas0809/kickstarter-analysis/blob/342f411fb15f9338225e12c43ed375d9cc5a4d49/Resources/Additional%20Resources/auto%20fit%20cell%20sizze%20and%20width.png)
        
### Formatting the spreadsheet 
- The normal cell widht does not capture the entire value of currency amount in spreadsheet.So,we changed the goal and pledged coloumn data type to "scientific"".

- We used the freezing feature of excel to lock top row so that it is always displayed no matter what part of sheet we sre looking into.

- There are four differnt types of outcomes i.e successfull,canceled,live and failed.We performed some basic conditional formatting to chage the colour of specific cells.For example the successfull camaping cell outcome is colour filled with green and dark green text color.The challange i faced while performing this task was the text spelling.Text should ne exact match.For exapmple i entered "cancelled" in text box and it is spelled "cancel" in spreadsheet.
    
### Data conversion.</br>

The date started and Date ended coloumn has unix time stamp.This means time(in seconds) differnece btween any given date and Unix Epoch(Jan 1,1970).We use the converion formula to convert unix time into normal time.The time is now in decimal format.So,next step is to change datatype of coloumn into Short Date/Long date to make it human readable.

        =(J3/86400)+DATE(1970,1,1)        

The challange was second part in this as i was confused that why i am not getting the date as result.
        
### Calculated Coloumns.

After the formatting and orgainizing,now it is time to crunch some number and create some calculated columns which are required to perform our analysis.

- Average Donation:Average donation is calculated ny dividing pledge amount by backer count.We also used ROUND function to round off result by 2 decimal places.

        =IFERROR(ROUND(E2/L2,2),0)
        
The challange in this task was divide by zero error.There are some events with 0 backers,so ther result was giving #DIV/0!.We used IFERROR function to give us 0 when the error encounters.
        
- Extracting Year from Date:We created new column for Year.We extraced year from Date started using YEAR function.

        =YEAR(S3)    
        
- Total Duration of Campaign:We created another coloumn which gives us total duation of the campaign which is differnce between Date Started and Date Ended coloumn.For that,we used DATEDIF function to get number of days for which the campaign ran.

        =DATEDIF(S2,T2,"d")        
        
### Creating Subcategories 

In our spreadsheet,we have "category and subcategory" coloumn for the event.For our analysis,we divided that into two differnt colummns i.e. "Parent Category" and "Subcategory".

For that we use,Text to column function under the Data tab in excel.
        
### Analysis of Outcomes Based on Launch Date.

As per requirement,we did analysis on outcome based om when they are launched in a particular year.We created a pivot table to show total of outcomes divided into different categories by month sorted by Parent Caregory.This particular analysis is for theatre events.

There were no issues that i ran into while performing this task.If we break down requirements into different parts before making our pivot table,things gets super easy.But there was a confusion as the requirement in assignment was not clear.There are all steps listed in order except to filter out live events before we make a pivotchart.A possible issue that someone can ran into is the date hierarchy.Excel automatically coverts the date in to hierarechy.We have to remove or rearrange that to get the desired results.
    
### Analysis of Outcomes Based on Goals

We divided the goal amount into differnt slabs ranging from "Les than 1000" to "greater than 50000".We created calculated coloum which counts number of specific item i.e count of successull,failed and canceled projects under specific criteria.

For goal amount less than 1000,is successfull and is category plays.

        =COUNTIFS(Kickstarter!D:D,"<1000",Kickstarter!F:F,"successful",Kickstarter!R:R,"plays")
        
For goal amount between 5000-9999,is successfull and is category plays.

        =COUNTIFS(Kickstarter!D:D,">=5000",Kickstarter!D:D,"<=9999",Kickstarter!F:F,"successful",Kickstarter!R:R,"plays")
        
After that we calculated the percenatge of events and created one line chart to represent the trend.
        

The issue that i ran into was using COUNTIF function.This function does not work for multiple criterias.We had to use COUNTIFS for that.

Another issue was that criteria has to be included in "".It is very easy to get confused and code wont return the right result.

Third issue i faced was while adding conditions in COUNTIFS function.For events with goal >= 50000,i missed = and it didnt count all the evennts with goal of 50,000.

        =COUNTIFS(Kickstarter!D:D,">=50000",Kickstarter!F:F,"successful",Kickstarter!R:R,"plays")
        
## Results

### What are two conclusions you can draw about the Outcomes based on Launch Date?

- We noticed that most successfull month in entire campaign is May with 111 camapaigns followed by June with 100 successfull outcomes and July at third place with 87 total oucomes.We can say that summer is the most succesfull time of the year to run campaigns.
    
- Our top 3 months with sucessfull campaign also tops in total number of events respectively executed by Louise.
    
- Another thing worth noticing is month of October.There is no cancelled campaignn in month of October.
    
- Deember is the month with least percentage of successfull campaigns.Also,this is the slowest month for our campaign period.Louise did least ie. 75 camapigns in month of December.

### What can you conclude about the Outcomes based on Goals?

Following are the outcomes of the analysis

- There is no cacelled event for category "plays".

- There is 0% success rate in camapaings where the goal amount is between 45000-49999.

- Sucess rate is 50-50 in campaings where goal is between 15000-19999.

- The most number of project goal range from 1000-4999.

### What are some limitations of this dataset?





### What are some other possible tables and/or graphs that we could create?


- Average number of backer counts by country


- Average Donation by Category


- Number of camapaigns by Category


- Different outcomes based on categories

