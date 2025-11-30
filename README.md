# EMPLOYEE SELF-SERVICE: LEAVE MANAGEMENT SOLUTION

## I. EXECUTIVE SUMMARY & SOLUTION ARCHITECTURE
This project demonstrates the successful integration of **Power Apps**, **Power Automate**, and **SharePoint** to create a single, automated, and paperless **HR Process Automation**.

- **Objective:** To replace manual email processes with a reliable application frontend, and automate the managerial approval and database update steps.
- **Integration Point:** SharePoint Online List serves as the central database and connector between all components.

***

## II. POWER APPS: FRONTEND & DATA SUBMISSION LOGIC

This section highlights the **User Interface (UI/UX)** development and the stable data submission method used.

- **Component Focus:** Power Apps Canvas App.
- **Process:** Employee inputs data into the form and clicks submit. The data is directly sent to SharePoint.

### Visual Proof (Frontend)
![Simple UI of the Power Apps]([LINK_GAMBAR_APP_UI_DI_SINI](https://github.com/divabintang/HR_Leave_Request_Automation_App/blob/main/App_UI_Screenshot.jpeg))

### Formula (Proof of Skill)
The submission logic is implemented using the industry standard for **direct data binding**, which ensures stability and avoids reliance on external flow triggers for submission:

| Location | Formula | Purpose |
| :--- | :--- | :--- |
| Button OnSelect | `NewForm(EditForm1); SubmitForm(EditForm1); Notify(...); ResetForm(EditForm1)` | force the form into 'New' mode and execute a direct data submission to the SharePoint database. |

***

## III. POWER AUTOMATE: APPROVAL & WORKFLOW LOGIC

This section highlights the **Process Automation** capabilities, including conditional logic and robust system integration.

- **Component Focus:** Cloud Flow, Approvals Connector.
- **Workflow Goal:** Manage request routing and automatically update the database based on the manager's decision.

### Visual Proof (Workflow Diagram)
![Flowchart in Power Automate](https://github.com/divabintang/HR_Leave_Request_Automation_App/blob/main/Flow_Chart_Diagram.pdf)

### Proof of Success (Run History)
![Run History]([LINK_GAMBAR_RUN_HISTORY_DI_SINI](https://github.com/divabintang/HR_Leave_Request_Automation_App/blob/main/Flow_Run_Success.jpeg))

### Key Workflow Logic
1.  **Trigger:** Flow is triggered manually (simulating the app submission).
2.  **Approvals Connector:** Sends a standard approval request email to the manager specified in the app input.
3.  **Conditional Branching (IF/ELSE):** The flow awaits the manager's response:
    * **IF Approved:** **Update item** in the SharePoint List to status **'Approved'**.  
    * **IF Rejected:** **Update item** in the SharePoint List to status **'Rejected'** and send a rejection notification email to the employee.


***

## IV. DATA INTEGRITY PROOF (SharePoint)
[*The test data evidence file is uploaded to the repository..*](https://github.com/divabintang/HR_Leave_Request_Automation_App/blob/main/SharePoint_Data_Proof.jpeg)
