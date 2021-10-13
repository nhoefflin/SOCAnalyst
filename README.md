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
  - I designed the following visualizations and added them to a dashboard called "Windows Server Monitoring":

#### Signature Field Values Over Time.
  - [Signature Field Values](Images/sig1.png)

#### Count of Different Signatures
  - [Count of Different Signatures](Images/sig2.png)

#### User Field Values Over Time
  - [User Field Values](Images/user1.png)

#### Count of Different Users
  - [Count of Different Users](Images/user2.png)




## Apache Logs
