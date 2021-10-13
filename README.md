# SOCAnalyst


## Scenario:
- In this activity I play the role of a SOC analyst at a small company called Virtual Space Industries (VSI).

  - VSI has heard rumors that a competitor, JobeCorp, may be launching cyberattacks to disrupt VSI's business.
  - As a SOC analyst, I am tasked with using Splunk to monitor against potential attacks on our systems and applications.
  - The Networking team has provided me with past logs to help me develop baselines and create reports, alerts, and dashboards.
    - Windows Server Logs
      - This server contains intellectual property of VSI's next-generation virtual reality programs.
    - Apache Server Logs
      - This server is used for VSI's main public-facing website vsi-company.com.

# Part 1: Master of the SOC

## Windows Server Logs


### Reports
  - I designed the following reports to assist VSI with quickly identifying specific information:

#### SignatureID
  - A report with a table of signatures and associated SignatureID.
  - This will allow VSI to easily view reports that show the ID number with a specific signature of the Windows activity.
    - [Syntax](Images/signatureID1.png)
    - [SignatureID Report](Images/signatureID2.png)

#### Severity
  - A report that provides the count and percent of the severity.
  - This will allow VSI to quickly know the severity levels of the Windows logs being viewed.
    - [Syntax](Images/severity1.png)
    - [Severity Report](Images/severity2.png)

#### Windows Activities
  - A report that provides a comparison between the success and failure of Windows activities.
  - This will show VSI if there is a suspicious level of failed activities on their server.
    - [Syntax](Images/windows1.png)
    - [Windows Activities Report](Images/windows2.png)


### Alerts
  - I designed the following alerts to notify VSI of suspicious activity:

#### Failed Windows Logons
- The average activity per hour is approximately six events. I set an alert to trigger after 15 or more events.
  - [Syntax](Images/failed1.png)
  - [Failed Login Alert](Images/failed2.png)

#### Successful Windows Logons
- The average activity per hour is approximately 12 events. I set an alert to trigger after 30 or more events.
  - [Syntax](Images/success1.png)
  - [Successful Login Alert](Images/success2.png)

#### A User Account Was Deleted
  - The average activity per hour is approximately 13 events. I set an alert to trigger after 30 or more events.  
    - [Syntax](Images/deleted1.png)
    - [Deleted Account Alert](Images/deleted2.png)



### Visualizations and Dashboards
  - I designed the following visualizations and added them to a dashboard called "Windows Server Monitoring:"

#### Signature Field Values Over Time.
  - [Signature Field Values](Images/sig1.png)

#### Count of Different Signatures
  - [Count of Different Signatures](Images/sig2.png)

#### User Field Values Over Time
  - [User Field Values](Images/user1.png)

#### Count of Different Users
  - [Count of Different Users](Images/user2.png)


## Apache Server Log

### Reports

#### HTTP Methods
  - A report that shows a table of the different HTTP methods (GET, POST, HEAD, etc).
  - This will provide insight into the type of HTTP activity being requested against their web server.
    - [Syntax](Images/method1.png)
    - [HTTP Methods Report](Images/method2.png)

#### Top 10 Domains
  - A report that shows the top 10 domains that referred to VSI's website.
  - This will assist VSI with identifying suspicious referrers.
    - [Syntax](Images/domain1.png)
    - [Top Domains Report](Images/domain2.png)

#### HTTP Response Codes
  - A report that shows the count of the HTTP response codes.
  - This will provide insight into any suspicious levels of HTTP responses.
    - [Syntax](Images/http1.png)
    - [HTTP Response Codes Report](Images/http2.png)

### Alerts

#### Hourly Activity Outside the U.S.
  - The average activity per hour is approximately 80. I set an alert to trigger after 170 or more events.
    - [Syntax](Images/clientip1.png)
    - [ClientIP Outside U.S. Alert](Images/clientip2.png)

#### HTTP POST Method
  - The average activity per hour is approximately two. I set an alert to trigger after 12 or more events.
    - [Syntax](Images/post1.png)
    - [HTTP POST Method Alert](Images/post2.png)

### Visualizations and Dashboards
  - I designed the following visualization and added them to a dashboard called "Apache WebServer Monitoring:"

#### HTTP Methods Over Time
  - [HTTP Count by Method](Images/method4.png)

#### Location Based on Client IP
  - [GeoStats](Images/geo1.png)

#### Count of Different URIs
  - [Count of URIs](Images/uri1.png)

#### Count of Top 10 Countries
  - [Top Countries](Images/countries1.png)

#### Different User Agents
  - [Statistical Chart of User Agents](Images/agents1.png)


# Part 2: Defending the SOC
  - VSI recently experienced several cyberattacks, likely from their adversary JobeCorp.
  - Fortunately, the SOC team had set up several monitoring solutions to help VSI quickly identify what was attacked.
  - These monitoring solutions will also help VSI create mitigation strategies to protect the organization.
    - I have been provided two log files of suspicious activity:
      - Windows Server Attack Log
      - Apache Server Attack Log
## Windows Server Attack Log

### Report Analysis for Severity
  - I did detect changes in severity which indicates an increase in the high severity cases. The percentage change can be seen below:
    - [Baseline Severity](Images/severity3.png)
    - [Severity After Attack](Images/severity4.png)

### Report Analysis for Failed Activities
  - I did detect changes in failed windows activities, however, there wasn't a major change in the cumulative failure of events.
    - [Baseline Failed Activities](Images/windows3.png)
    - [Failed Activities After Attack](Images/windows4.png)

### Alert Analysis for Failed Logons
  - There is some potential suspicious activity for failed logons at 8 a.m. on Weds, March 25th.
  - The count of activity is 35 events during this hour. Which can be seen below:
    - [Failed Logons](Images/failed3.png)

### Alert Analysis for Successful Logons
  - There is some potential suspicious activity for failed activity at 11 a.m and 12 p.m. on Weds, March 25th.
  - The count of activity is 196 at 11 a.m. and 77 at 12 p.m. which can be seen below.
    - [Successful Logons](Images/logon1.png)
    - [Successful Logons](Images/logon2.png)


### Alert Analysis for Deleted Accounts
  - There was no suspicious activity of deleted accounts.

### Dashboard Analysis for Time Chart of Signatures
  - The signatures that have suspicious activity are: User account was locked out, attempt was made to reset a users password, and an account was successfully logged on.
    - User account was locked out: Started around 1 a.m. and ended at 3 a.m. on March 25th. The peak count was 896.
      - [User Account Locked Out](Images/sig3.png)
    -  An attempt was made to reset a users password: Started around 9 a.m. and ended at 11 a.m. on March 25th. The peak count was 1,258.
        - [Reset a User Password](Images/sig4.png)
    - The account was successfully logged on: Started around 11 a.m. and ended at 1 p.m. on March 25th. The peak count was 196.
        - [Successful Logon](Images/sig5.png)


### Dashboard Analysis for Users
  - The users that have suspicious activity are users A, K, and J.
    - User A: Started around 1 a.m. and ended at 3 a.m. on March 25th. Peak count was 985.
      - [User A](Images/user3.png)
    - User K: Started around 9 a.m. and ended at 11 AM on March 25th.  Peak count was 1,256.
      - [User K](Images/user4.png)
    - User J: Started around 11 a.m. and ended at 1 p.m. on March 25th. Peak count was 196.
      - [User J](Images/user5.png)

### Dashboard Analysis for Signatures & Users
  - Here is a clean dashboard visual of signatures and users discussed above:
    - [Dashboard](Images/dashboard1.png)

## Apache Server Attack Log
