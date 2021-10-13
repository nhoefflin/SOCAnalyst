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

#### Failed Windows Login
- The average activity per hour is approximately six events. I set an alert to trigger after 15 or more events.
  - [Syntax](Images/failed1.png)
  - [Failed Login Alert](Images/failed2.png)

#### Successful Windows Login
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


## Apache Logs

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

## Report Analysis for severity
  - I did detect changes in severity, which indicates an increase in the high severity cases. The percentage change can be seen below:
    - [Normal Severity](Images/severity3.png)
    - [Severity After Attack](Images/severity4.png)
