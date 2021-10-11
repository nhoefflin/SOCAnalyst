# SOCAnalyst


## Scenario:
- In this activity I play the role of a SOC analyst at a small company called Virtual Space Industries (VSI).

  - VSI has heard rumors that a competitor, JobeCorp, may be launching cyberattacks to disrupt VSI's business.
  - As a SOC analyst, I am tasked with using Splunk to monitor against potential attacks on our systems and applications.
  - The Networking team has provided me with past logs to help me develop baselines and create reports, alerts, and dashboards.

## Windows Server Logs
I designed the following to assist VSI with quickly identifying specific information:

### reports

#### SignatureID
  - A report with a table of signatures and associated SignatureID.
  - This will allow VSI to easily view reports that show the ID number with a specific signature of the Windows activity.

[Syntax](Images/signatureID1.png)

[SignatureID Report](Images/signatureID2.png)

#### Severity
  - A report that provides the count and percent of the severity.
  - This will allow VSI to quickly know the severity levels of the Windows logs being viewed.

[Syntax](Images/severity1.png)

[Severity Report](Images/severity2.png)

#### Windows Activities
  - A report that provides a comparison between the success and failure of Windows activities.
  - This will show VSI if there is a suspicious level of failed activities on their server.

[Syntax](Images/windows1.png)

[Windows Activities Report](Images/windows2.png)


## Alerts


## Dashboards
