### 311 NYC Service report

#### Dataset 
311 NYC dataset for data from Jul 2025 to Dec 2025 (Excel file)

#### Report Overview

**Overview**

![Overview](https://github.com/tanushreeshingane/311-service-request/blob/main/311%20service%20report%20overview%20page.jpg)

**Regional Analysis**

![Regional Analysis](https://github.com/tanushreeshingane/311-service-request/blob/main/311%20service%20report%20regional%20analysis%20page.jpg)

**Agency Performance**

![Agency Performance](https://github.com/tanushreeshingane/311-service-request/blob/main/311%20service%20report%20agency%20performance%20page.jpg)


Due to large file size, the .pbix file has been hosted 
externally.

[Download report](https://1drv.ms/u/c/d10314ef347b950b/IQBukkJltchrRJnOaQDTBAz5AQLMSQRVxxTdZMWH9TAr94U?e=u3N29r)


#### Problem statement 
Several non emergency problems are reported to 311 in New York City each month. The city administration aims to understand the problem volume and the key insights regarding the problems to handle them more efficiently. 

#### Objective
The report aims to explore the 311 Service Request data from July 2025 to December 2025 for the city of New York and explore the types of problems and the key factors affecting the problems. The report also aims to suggest some actionable insights based on the given data. 

#### Dataset Overview
Number of rows (problems) - ~18,80,000

Source - [311 NYC Service data](https://data.cityofnewyork.us/Social-Services/311-Service-Requests-from-2020-to-Present/erm2-nwe9/about_data)

The data was queried from Jul 2025 to Dec 2025 and downloaded as an Excel file. 

[Download Excel file](https://1drv.ms/u/c/d10314ef347b950b/IQAxJMAn5ImDRJprH7SAAJxFAZWMrAp6cd6zwRS1EQHLz9M?e=rihiAq)

##### Key Fields 
1) Unique Key
2) Problem (formerly Complaint Type)
3) Created Date
4) Closed Date
5) Borough
6) Latitude
7) Longitude
8) Location
9) Agency Name
10) Status


#### Insights
1) The maximum number of complaints are reported between 10 am to 5 pm and after 8 pm, showing that people prefer to report complaints during working hours or after dinner. 
2) The most frequently reported issue is Illegal parking with peak reporting hours from 8 am to 11 am and between 8 pm to 9 pm. The illegal parking is most frequently reported in borough Queens.
3) The complaint volume shoots up to about 17% in October, indicating a seasonal increase in service demand.
4) People prefer to report a complaint online than the traditional means, showing good adoption of digital reporting channels. 
5) The average resolution time is between 6-8 days between boroughs, although when borough is unspecified the resolution time is greater. 
6) The most complaints are reported from Brooklyn .
7) The hotspot area with the most number of complaints is in Bronx borough with frequent complaints for noise. 
8) NYPD handles the highest volume of complaints and maintains a high closure rate, indicating high efficiency.
9) Economic Development Corporation has the highest open complaint % (100%) indicating backlog in resolution of complaints despite high volume of complaints. 


#### Recommendations
1) Promote the digital reporting channels further.
2) Allocate more resources to boroughs like Brooklyn where the volume of complaints is high.
3) Hotspot areas with frequent complaint reports (like noise) should be investigated for root cause of the issue. 
4) Illegal parking prevention measures during peak hours can be implemented. Also more parking spaces should be made available in Queens to curb illegal parking. Strict penalties for repeat offenders in hotspot areas can also be implemented.
5) Improve resolution efficiency for agencies where the open complaint % is high. 


#### Tools & Technologies
Power BI Desktop


#### Data Preparation 
1) Calculated resolution time by date difference between Created Date and closed date  for closed status problems - Resolution Time (Derived column).
2) Extracted hour from Created date - Reporting Hour (Derived column).
3) Removed rows where Resolution Time was less than 0 (Incorrect data).
4) Removed several unused columns like Problem detail, Incident ZIP, Resolution Description,Street Name etc.
5) Formatted Text in columns like Borough, Problem and Open Data Channel Type (Formatting).

#### Key Metrics / Measures 

1) Total Complaints 

2) Average Resolution Time

3) Closure Rate 
	
			      var closed_count = CALCULATE(COUNT('311_data'[Unique Key]),'311_data'[Status]="Closed")
            var total_count = COUNT('311_data'[Unique Key])

            return  DIVIDE(closed_count,total_count)

4) Open Complaint % 
			
            var total_complaints = CALCULATE(COUNT('311_data'[Unique Key]),ALLEXCEPT('311_data','311_data'[Agency Name]))
			      var open_count = CALCULATE(COUNT('311_data'[Unique Key]),'311_data'[Status]<>"Closed")
			
			      return DIVIDE(open_count,  total_complaints)
			

#### Dashboard features
1) Filter - Reporting date filter on all the pages.
2) Drill down feature - Complaint volume trend by month and dates.
3) Time based analysis - Complaint volume trend by month and dates.
4) Comparison of agency wise performance of complaints, borough wise comparision of complaints.
5) Maps to show locations with high complaint volume.

#### Skills Demonstrated 
1) Data Cleaning (using Power Query)
2) Data visualization design
3) Analytical Thinking
4) DAX
5) KPI design

#### Icon attributions 
1) Total complaints icon - <a href="https://www.flaticon.com/free-icons/complaint" title="complaint icons">Complaint icons created by Freepik - Flaticon</a>
 
2) Closed complaints icon -  <a href="https://www.flaticon.com/free-icons/resolve" title="resolve icons">Resolve icons created by Dinnicon - Flaticon</a>  

3) Open complaints icon - <a href="https://www.flaticon.com/free-icons/problem" title="problem icons">Problem icons created by Freepik - Flaticon</a>

4) Resolution time icon - <a href="https://www.flaticon.com/free-icons/duration" title="duration icons">Duration icons created by Uniconlabs - Flaticon</a>


#### Limitations
1) Data limited to July–December 2025
2) Some records contain missing or unspecified fields (e.g., borough, channel type)
3) Analysis is based on reported complaints and may not reflect unreported issues


#### Contact 
[LinkedIn](https://www.linkedin.com/in/tanushree-shingane/)

[Email](mailto:tanushreeshingane@gmail.com)
