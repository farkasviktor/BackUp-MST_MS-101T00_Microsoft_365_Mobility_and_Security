# Module 3 - Lab 3 - Exercise 4 - Implement Mailbox Permission Alert


In this exercise you will configure and test an alert that will notify Lynne Robbins when FullAccess permissions are granted to any mailbox within Adatum.

### Task 1 – Create a Mailbox Permission Alert

1. You should still be logged into your Client 1 VM (LON-CL1) as the **Admin** account and into Microsoft 365 as Holly Dickson (**holly@xxxxxZZZZZZ.onmicrosoft.com)** with a password of **Pa55w.rd**. 

2. **Microsoft 365 Defender** should still be open in your Edge browser from the prior task. In the left-hand navigation pane, under the **Email & collaboration** section, select **Policies & rules**. 

3. On the **Policies & rules** window, select **Alert policy**.

4. In the **Alert policy** window, select **+New alert policy** on the menu bar.

5. In the **New alert policy** window, enter the following information:

	- Name: **Mailbox permission change**

	- Description: **This alert notifies Lynne Robbins when FullAccess permissions are granted to any mailbox in Adatum Corp.**

	- Severity: **Medium**

	- Category: **Permissions**

6. Select **Next.**

7. On the **Choose an activity, conditions and when to trigger the alert** window, enter the following information:

	- Activity is: select the drop-down arrow in the field, enter **mail** in the search box, and select **Granted mailbox permission**

	- How do you want the alert to be triggered? **Every time an activity matches the rule**

8. Select **Next.**

9. On the **Decide if you want to notify people when this alert is triggered** window, enter the following information:

	- Email recipients: Select the "X" to the right of **Holly Dickson's** account to remove her, enter **Lynne**, and then select **Lynne Robbins** from the user list

	- Daily notification limit: **No limit**

10. Select **Next.**

11. On the **Review your settings** page, review the settings and if anything needs to be corrected, select its corresponding **Edit** option and make the necessary corrections. When everything is correct, verify the **Yes, turn it on right away** option is selected (select it if necessary) and then select **Finish**.

12. Verify your new alert policy appears in the list on the **Alert policy** page and its **Status** in **On**.

13. Leave the Client 1 VM and the Alert policy tab in your Edge browser open for the next task.

You have now created an activity alert in Microsoft 365 Defender that is triggered when FullAccess permissions are granted to any mailboxes.


### Task 2 – Validate the Mailbox Permission Alert

In the prior task, you configured an alert that will notify Lynne Robbins when FullAccess permissions are granted to any mailbox within Adatum. To test this alert, Holly Dickson will change the FullAccess permission on Alex Wilber’s mailbox by granting Joni Sherman FullAccess to his mailbox. This activity should trigger the alert policy that you just created, which should send an alert notification email to Lynne Robbins’ mailbox. You will then log into the Client 2 VM as Lynne Robbins and see if she received this email. 

1. You should still be logged into the Client 1 VM (LON-CL1) as the **Admin** account, and you should still be logged into Microsoft 365 as **Holly Dickson**. 

2. In your Edge browser, select the **Microsoft 365 admin center** tab, and then in the left-hand navigation pane, under the **Admin centers** group, select **Exchange**. This opens the Exchange admin center for Exchange Online.

3. In the **Exchange admin center**, the **Mailboxes** window appears by default (if it doesn't, then in the left-hand navigation pane, under the **Recipients** group, select **Mailboxes**). 

4. In the **Mailboxes** window, select **Alex Wilber** from the list of mailboxes (select Alex's name; do not select the check mark to the left of his name).

5. In the **Alex Wilber** pane that appears, the **General** tab is displayed by default. Select the **Deletgation** tab.

6. On the **Manage mailbox delegation** pane, there are three mailbox permissions that can be updated: **Read and manage**, **Send as**, and **Send on behalf**. You want to add each of these permissions for Alex's mailbox to **Joni Sherman**. For each permission, perform the following steps to add Joni to that permission: <br/>

	- Select the **Edit** button for the permission. 
	- Select the **+Add permissions** button at the top of the pane.
	- In the list of users that appears, select the check box for **Joni Sherman** and then select **Save**.
	- Once the mailbox permission is added, select the back arrow at the top of the pane. 
	- This displays Joni as having the permission that you just edited. At the top of the pane, select the back arrow to return to the **Manage mailbox delegation** pane, which displays the three permissions. Repeat these steps for each of the three permissions. 

7. Once you have assigned Joni to each of the three permissions on the **Manage mailbox delegation** pane, select the **X** in the upper right-hand corner to close the pane. 

8. In the **Alex Wilber** pane, select the **X** in the upper right-hand corner to close the pane. 

9. Since **Holly Dickson** has changed the mailbox permissions for Alex Wilbur by giving Joni Sherman full access permissions to his mailbox, an alert email should automatically be sent to Lynne Robbins’ Inbox that notifies her of this event.

	‎Switch to LON-CL2. 

10. In your Edge browser, select the **Mail - Lynne Robbins - Outlook** tab that has Outlook on the web open for Lynne Robbins' mailbox. In Lynne Robbins’ **Inbox**, an email should be received from the Alerts notification system (**Office365Alerts@microsoft.com**) to let her know that Holly Dickson has made a Mailbox permission change. <br/>

	**Note:** In can take up to 15 minutes or so for the email to be received in Lynne's Inbox. 

11. Open the email and review the contents. Scroll to the bottom of the email and select the **View alert details** button. This opens the **Security and Compliance Center**, displays the **View alerts** window, and opens the **Mailbox permission change** alert. <br/>

	Scroll down through the **Mailbox permission change** alert and review all the information. When you are done, select **Close** to close the **Mailbox permission change** alert, then close the **View alerts** tab in your browser.

12. Switch back to the LON-CL1.

13. In the **Microsoft 365 Security &amp; Compliance center** left-hand navigation pane, select **Incidents & alerts** to expand the group select **Alerts,** and then under it, select **View Alerts**. The notification that was just created based on the **Mailbox permission change** alert should appear in the list.

14. In your browser, close the Exchange admin center tab (**mailboxes - Microsoft Exchange**), but leave the other browser tabs open.

15. Leave your LON-CL1 and LON-CL2 VMs open for the remaining tasks in this lab.

You have just successfully tested a mailbox permission alert that sent an alarm message on granting FullAccess to a user mailbox.

# Proceed to Lab 3 - Exercise 5
