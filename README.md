# kickstarter-analysis
Performing analysis on Louise Kickstarter to uncover various trends
# Kickstarting with Excel

## Overview of Project

    This project performs the data and visual analysis of a crowdfunding project run by up-and-coming playwright, Louise. With a very limited budget of $10,000, she is hesitant about her first fundraising campaign. So, we are helping her to crunch some number and visualize the various trends which help Louise to make her very important decisions to make her campaign successful.

    She ran in total of 4114 campaigns in 21 different countries. The response was amazing, she had very successful campaign with total of 2185 campaign. There were some unsuccessful campaigns which were 1530 in total. United States is the country where she ran her most of campaigns.

    The main analysis tool we used is Microsoft Excel. Excel is a powerful tool to perform wide range of data visualization operations.

    By the end of this project, we will see various trends and key factors which are visualized by various bar-charts, line-charts and pivot tables to analyze the campaign.

## Analysis and Challenges

*Basic structure </br>

    The overview of the dataset is very boring and unorgainzed.We performed some basic formatting steps to make the tabular data look more presentable and easy to read.
        1.The first operation we performed was to auto-adjust width and height of the cells to make the data fit in the cell and easily readable.
        
     
*Formatting the spreadsheet</br>

    1.The normal cell widht does not capture the entire value of currency amount in spreadsheet.So,we changed the goal and pledged coloumn data type to "scientific"".</br>
    
    2.We used the frrezing feature of excel to lock top row so that it is always displayed no matter what part of sheet we sre looking into.</br>
    
    3.  There are four differnt types of outcomes i.e successfull,canceled,live and failed.We performed some basic conditional formatting to chage the colour of specific cells.For example the successfull camaping cell outcome is colour filled with green and dark green text color.The challange i faced while performing this task was the text spelling.Text should ne exact match.For exapmple i entered "cancelled" in text box and it is spelled "cancel" in spreadsheet.</br>
    
*Data conversion.</br>

    The date started and Date ended coloumn has unix time stamp.This means time(in seconds) differnece btween any given date and Unix Epoch(Jan 1,1970).We use the converion formula to convert unix time into normal time.The time is now in decimal format.So,next step is to change datatype of coloumn into Short Date/Long date to make it human readable.</br>
    
        The challange was second part in this as i was confused that why i am not getting the date as result.</br>
        
*Calculated Coloumns.</br>

    After the formatting and orgainizing,now it is time to crunch some number and create some calculated columns which are required to perform our analysis.</br>
        1.Average Donation:Average donation is calculated ny dividing pledge amount by backer count.We also used ROUND function to round off result by 2 decimal palces.</br>
        
            The challange in this task was divide by zero error.There are some events with 0 backers,so ther result was giving #DIV/0!.We used IFERROR function to give us 0 when the error encounters.</br>
            
        2.Extracting Year from Date:We created new column for Year.We extraced year from Date started using YEAR function.</br>
        
        3.Total Duration of Campaign:We created another coloumn which gives us total duation of the campaign which is differnce between Date Started and Date Ended coloumn.For that,we used DATEDIF function to get number of days for which the campaign ran.</br>
        
*Creating Subcategories</br>

    In our spreadsheet,we have "category and subcategory" coloumn for the event.For our analysis,we divided that into two differnt colummns i.e. "Parent Category" and "Subcategory"."</br>
    
    For that we use,Text to column function under the Data tab in excel.</br>
    
        
### Analysis of Outcomes Based on Launch Date.

    As per requirement,we did analysis on outcome based om when they are launched in a particular year.We created a pivot table to show total of outcomes divided into different categories by month sorted by Parent Caregory.
    
    *We noticed that most successfull month in entire campaign is May with 111 camapaigns followed by June with 100 successfull outcomes and July at third place with 87 total oucomes.We can say that summer is the most succesfull time of the year to run campaigns.
    
    *Our top 3 months with sucessfull campaign also tops in total number of events respectively executed by Louise.
    
    *Another thing worth noticing is month of October.There is no cancelled campaignn in month of October.
    
    *Deember is the month with least percentage of successfull campaigns.Also,this is the slowest month for our campaign period.Louise did least ie. 75 camapigns in month of December

    

### Analysis of Outcomes Based on Goals



## Results

- What are two conclusions you can draw about the Outcomes based on Launch Date?

- What can you conclude about the Outcomes based on Goals?

- What are some limitations of this dataset?

- What are some other possible tables and/or graphs that we could create?

