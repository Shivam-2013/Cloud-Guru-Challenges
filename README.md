# Cloud-Challenges
## Step1-  Python code for data manuplation 

**TRANSFORMATION**. Perform data manipulations in Python code. 
       
**CLEANING** – The date field should be converted to a date object, not a string.

**JOINING** – We want to show recovered cases as well as confirmed cases and deaths. The NYT data does not track recoveries, 
so you will need to pull US recovery data from Johns Hopkins dataset and merge it into your record for each day. 
            
_Note: the case and death counts for the Johns Hopkins dataset disagree with the NYT data. 
We will treat the NYT data as authoritative and only copy the recovery data from Johns Hopkins_.)

**FILTERING** – Remove non-US data from the Johns Hopkins dataset. Remove any days that do not exist in both datasets.
    (There is an off-by-one issue.)
