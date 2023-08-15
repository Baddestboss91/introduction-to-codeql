<!--
  <<< Author notes: Step 2 >>>
  Start this step by acknowledging the previous step.
  Define terms and link to docs.github.com.
  TBD-step-2-notes.
-->

## Step 2: Review and Triage CodeQL Alerts

_Way to go! You got CodeQL running! :tada:_

In this exercise, we'll review the CodeQL scan results, triage an alert, and create a GitHub issue to track an alert.

**What is GitHub Actions**: GitHub Actions is the automation and CI/CD platform within GitHub. We use GitHub Actions to orchestrate and execute security scans with code scanning. GitHub Actions is a continuous integration and continuous delivery (CI/CD) platform that allows you to automate your build, test, and deployment pipeline. For more information on GitHub Actions, see "[Understanding GitHub Actions](https://docs.github.com/en/actions/learn-github-actions/understanding-github-actions)."

**What is CWE**: Common Weakenss Enumeration (CWE) is a category system for hardware and software weaknesses and vulnerabilities. Think of it as a way to describe and categorize security issues in an application's source code. For more information on CWEs, see the Wikipedia article "[Common Weakness Enumeration](https://en.wikipedia.org/wiki/Common_Weakness_Enumeration)."

### :keyboard: Activity 1: View the status of a CodeQL scan

In this activity, we'll explore GitHub Actions to view the status of a CodeQL scan.  
1. In your new repository, go to your Actions page by selecting **Actions** from the top navigation bar. If the CodeQL Action run is still executing, you will see a yellow spinner indicating the scan is still in progress. This typically takes about 4 minutes to complete.
2. Select the run by clicking on **CodeQL Setup**.

![codeql-setup](images/codeql-setup.png)

Notice that more information is available inside the Actions run. Feel free to explore this section to view information such as the CodeQL logs, duration, status, and artifacts generated by CodeQL.

Once the scan is complete, a green check will show next to the execution.  
  
### :keyboard: Activity 2: View all CodeQL Alerts

In this activity, we will view the CodeQL findings in the Security page of your repository. The Security page is where all security related information is displayed. 

1. Navigate to the **Security** tab in the top navigation bar of your repository.  
2. Select **Code scanning** under the "Vulnerability alerts" heading in left-side navigation bar.

This screen will contain all the vulnerabilities identified by CodeQL inside this repository's codebase. Explore the different filters and search capabilities in this page. These filtering capabilities become very helpful when you're working with many findings!


### :keyboard: Activity 3: Review an Alert

In this activity, we will explore the alert UI. We'll review the data flow of the vulnerability, indentify what part of the code the alert impacts, and get more information about the alert.

**Alert status:** This section displays the current alert status (open or closed), identifies the branch where the scan detected the alert, and shows the timestamp of the alert.
  
![alert-status](images/alert-status.png)

**Location information:** This section describes which part of the code is vulnerable.  
  
![location-information](images/location-information.png)

**Paths:** Clicking on "Show paths" will give you additional insights into the alert's data flow. The modal shows us where the user input (we call that a "source") flows through the application until it's acted on (we call this the "sink"). This visualizes the flow of data through your application. 
  
**Recommendations:** This section provides a quick overview of the tool (CodeQL in this case), Rule ID, and even allows you to view the CodeQL query used to find this vulnerability. You can view the query by clicking **View source**. Additionally, this pane includes recommendations for fixing this vulnerability. Click **Show more** to view the full recommendation.

![recommendations](images/recommendations.png)

**Audit trail:** The audit trail shows the history of the alert. This trail will show the status as users mark an alert as closed or fix an alert in the code.

![audit-trail](images/audit-trail.png)

**Alert triage:** Use the buttons at the top right of the alert to triage or create a new issue for the alert. Don't do anything yet. We'll get into these buttons in a moment. 😄

**Additional info:** Finally, the right-side panel contains information such as tags, CWE information, and the severity of the alert
  ![additional-information.png](images/additiona-information.png)


### :keyboard: Activity 4: Dismiss an Alert
Now that we're familiar with the alert layout, let's work through the process of closing one.

1. Inside this same alert, click **Dismiss alert**, choose any reason for dismissal, and add a short note.
2. Click **Dismiss alert**.
3. At this point, the alert will change its state to "Dismissed". You can now see the change you made in the audit trail at the bottom of the alert.
4. Navigate back to **Security** > **Code scanning alerts**.  You'll see that you only have 1 alert listed.
5. Click **1 Closed**.  This will bring you to the closed alerts where you can view the alert you just closed.
   ![one-closed-alert.png](images/one-closed-alert.png)

7. (Optional) You can also reopen the alert by opening it, then selecting **Reopen alert**.

### :keyboard: Activity 5: Create a GitHub Issue for an Alert
This last step will show you how to create a GitHub Issue to track the work that goes into resolving a vulnerability. Issues provide a space for collaboration for a security problem and can be assigned to people or teams.
  
1. Open one of the open alerts that CodeQL from the scan.  
2. Click the green **Create issue** button at the top right of the alert. If you don't see this button, check the status of the alert to make sure it's an open alert.
3. Add any details you would like to include in the new issue form.  
4. Click **Submit new issue**.
5. To view the your issue, click **Issues** in the top navigation bar of your repository.
6. Wait about 20 seconds then refresh this page (the one you're following instructions from). [GitHub Actions](https://docs.github.com/en/actions) will automatically update to the next step.