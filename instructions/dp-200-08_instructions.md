# DP 200 - Implementing a Data Platform Solution
# Lab 8 - Securing Azure Data Platforms



## Lab objectives
  
After completing this lab, you will be able to:

1. Describe key security components
1. Secure Storage Accounts and Data Lake Storage
1. Secure Data Stores
1. Secure Streaming Data



> **IMPORTANT**: As you go through this lab, make a note of any issue(s) that you have encountered in any provisioning or configuration tasks and log it in the table in the document located at _\Labfiles\DP-200-Issues-Doc.docx_. Document the Lab number, note the technology, Describe the issue, and what was the resolution. Save this document as you will refer back to it in a later module.


## Exercise 1: Key security components
  
Estimated Time: 10 minutes

Individual exercise
  
The main tasks for this exercise are as follows:

1. Assessing Data and Storage Security Hygiene

### Task 1: Assessing Data and Storage Security Hygiene.

1. In the Azure portal tab, click **Security Center**.

    ![Security Center in the Azure Portal](Linked_Image_Files/M08-E01-T01-img01.png)

1. In the Security Center - Overview screen, under **Resource Security Hygiene**, click Data and Storage.

    ![Security Center - Data Storage in the Azure Portal](Linked_Image_Files/M08-E01-T01-img02.png)

1. Identify the top two key data and storage components that require attention.

    1. __Answers may vary_____
    1. __Answers may vary_____

> **Result**: After you completed this exercise, you have learned where you can look to identify any data and storage security weaknesses that is in your Azure subscription.


## Exercise 2: Securing Data Stores
  
Estimated Time: 15 minutes

Individual exercise
  
The main tasks for this exercise are as follows:

1. Enabling Auditing

1. Query the Database

1. View the Audit log

### Task 1: Enabling Auditing

1. In the Azure portal, in the blade, click **Resource groups**, and then click **awrgstudxx**, and then click on **awdlsstudxx**, where **xx** are your initials

1. In the Azure portal, in the blade, click Resource groups, and then click awrgstudxx, and then click on **AdventureWorksLT**.

1. In the deptdatabasesxx (sqlservicexx/AdventureWorksLT) screen, click on the **Auditing** blade.

1. Under **Auditing**, click on the **ON** button.

1. Select the checkbox next to **Storage**.

1. Click on **Storage Details - Configure**.

1. In the **Storage Setting** screen, click **Subscription - change storage subscription**, and then click your subscription.

1. In the **Storage Setting** screen, click **Storage Settings - Configure required settings**. In the **Choose storage account** screen, click **awsastudxx**

1. In the **Retention Days** text box, type **90**, and then click on **OK**.

    ![Configuring Auditing in the Azure Portal](Linked_Image_Files/M08-E04-T01-img01.png)

1. Click on **Save**.

### Task 2: Query the database

1. On the windows desktop, click on the **Start**, and type **"SQL Server"** and then click on **MIcrosoft SQL Server Management Studio 17**

1. In the **Connect to Server** dialog box, fill in the following details
    - Server Name: **sqlservicexx.database.windows.net**
    - Authentication: **SQL Server Authentication**
    - Username: **xxsqladmin**
    - Password: **P@ssw0r**

1. In the **Connect to Server** dialog box, click **Connect** 

> **Note**: An error message is returned as the password is incorrect. Type in the correct password of **P@Ssw0rd**.

1. Type in the correct password of **Pa55w.rd**

1. In **SQL Server Management Studio**, in Object Explorer, expand **AdventureWorksLT**, and then expand **Tables**.

1. Right click [SalesLT].[Customers] and then click **Select Top 1000 Rows**

### Task 2: View the Audit Log

1. Return to the Azure Portal. In the AdventureWorksLT (sqlservicexx/AdventureWorksLT) - Auditing screen, click on **View Audit Logs**

1. Note in the **Audit records** log file the **Failed Authentication** record. Close down the **Audit records** screen

    ![Viewing Audit records in the Azure Portal](Linked_Image_Files/M08-E04-T01-img02.png)

> **Result**: After you completed this exercise, you have enabled database auditing and verified that the auditing works.

## Exercise 3: Securing Streaming Data
  
Estimated Time: 15 minutes

Individual exercise
  
The main tasks for this exercise are as follows:

1. Changing Event Hub Permissions

### Task 1: Changing Event Hub Permissions

1. In the Azure portal, in the blade, click **Resource groups**, and then click **awrgstudxx**, and then click on **xx-phoneanalysis-ehn**, where **xx** are your initials

1. In the Azure portal, in the **xx-phoneanalysis-ehn**, where **xx** are your initials. Scroll to the bottom of the window, and click on **xx-phoneanalysis-eh** event hub.

1. To grant access to the event hub, click **Shared access policies**.

1. Under the **xx-phoneanalysis-eh - Shared access policies** screen, click on **phoneanalysis-eh-sap**.

1. Click on the checkbox next to the **Manage** permissions to remove it, and then click **Save**.

1. In the Azure portal, in the blade, click **Home**,

> **Result**: After you completed this exercise, you modified the security of an Event Hub Shared Access Policy.
