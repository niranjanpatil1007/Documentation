---
&nbsp;
&nbsp;
&nbsp;


![Company logo](Company logo Link)

# AXIS-ARD_Plus
## Release Notes 
## [Production Patch]
 ## _<Feb - 2025>_
 &nbsp;
&nbsp;
&nbsp;
 &nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;

---
### AUDIENCE
 • Clients 
 • Internal Users 
 STATEMENT OF CONFIDENTIALITY 
This document is the proprietary and confidential property of Pvt. Ltd. It is intended solely for use by employees and clients of Pvt. Ltd and shall not be reproduced or disclosed to any other party without the express written consent of Pvt. Ltd. The use, disclosure, reproduction, modification, transfer, or transmittal of this work for any purpose in any form or by any means without the written permission of Pvt. Ltd is strictly prohibited. 
    <div align="center">
**CONFIDENTIAL, UNPUBLISHED PROPERTY
OF
 PVT. LTD. 
USE AND DISTRIBUTION ARE LIMITED SOLELY TO AUTHORIZED PERSONNEL ONLY.
© Pvt. Ltd. 2022 All Rights Reserved** 

  </div>

 &nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;


---
---

### Revision History

| Sr. No | Date       | Version | Author           | Reviewer           |
|--------|------------|---------|------------------|--------------------|
| 1      | 07/02/2025 | 5.0     | Niranjan Patil   | KP |


### Document History

| Bank UAT Sign-Off Date | UAT Sign-Off by        |
|------------------------|------------------------|
| 30/01/2025             | Aditi            |

| Fable QA Sign-Off Date | QA Sign-Off by          |
|------------------------|-------------------------|
| 20/12/2024             | Sharon  |

 &nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;



---

---

### 1. Release Features

This release note lists the implementation of the Requirements mentioned in Point 2.

### 2. Issues, New Enhancements, And Change Request

| Sr No. | Description                      | Reference to Functionality/Enhancements/Defect Fixes/ESB | Workaround |
|--------|----------------------------------|----------------------------------------------------------|------------|
| 1      | Settlement Front End Tool Issue | Issue fixed                                              |            |

### 3. Resolutions

| Sr. No | Description                                                       |
|--------|-------------------------------------------------------------------|
| 1      | Settlement issue: settlement flag was going as a null value; fixed. |


### 4. Impact Analysis

* Transaction settlement flow should check post deployment.

### 5. Technical Specification: Prod server.

#### 5.1. Production JSP File

 **Path: onlinetransfer\ secure\ admin**

* [modifyCutoffSettlemenEntryTimeToolCheckerAction.jsp]()

#### 5.2. JS Files

NA

----

#### 5.3. JAR Files

NA

### 6. Deployment Steps

1. Stop the application before starting the deployment.

2. Take the back of the admin folder. Deploy the **JSP file** available in the JSP folder

in the patch file in jsp file deployment location (**secure/admin**).

3. Take the back of the existing file from the server. Add the JSP file mentioned in the

patch file. Keep a copy of the existing one.

4. Deleted the temp files.

5. Start the service by executing sh indusforexcard-start.sh command from the

location /**RH/jboss-eap-7.3/bin.**

6. Analise the server log and check if the application running.

### 7. Environment Details

NA

### 8. Web services or Esb changes

NA

### 9. Properties

NA
&nbsp;
&nbsp;

---
---

### 10. Transfer Query

NA

### 11. SQL SCRIPTS

NA

### 12. Deployment Plan

War backup should be carried out before deployment. All JARs and JSPs shall be reverted as per the back-up taken during the start of the deployment

### 13. Rollback plan for server

The Backup files should be moved to the respective server/folder from the location backup has been carried out.

### 14. Rollback plan for DB

NA
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;
&nbsp;


<div align="center">



</div>



----
