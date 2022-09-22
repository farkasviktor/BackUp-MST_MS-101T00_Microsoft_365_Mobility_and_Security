# Learning Path 4 - Lab 4 - Exercise 2 - Configure Retention Tags and Policies  

In this exercise, you will implement archiving with MRM retention tags. You will then configure retention tags and policies through the Microsoft Purview portal. 

### Task 1 – Activate In-Place Archiving

In this next phase of your Adatum pilot project, you will access the Microsoft Purview portal to activate Holly Dickson’s archive mailbox.   

1. You should still be logged into LON-CL1 as the **Admin** and into **Microsoft 365** as Holly Dickson.

2. In Microsoft Edge, in the **Microsoft 365 admin center**, under the **Admin centers** group, select **Compliance** to open the Microsoft Purview portal.

3. In the **Microsoft Purview** portal, in the left-hand navigation pane, select **Data lifecycle management** to expand the group, and then select **Microsoft 365**. 

4. On the **Data lifecycle management** page, the **Overview** tab appears by default. In the list of tabs along the top of the page, select **Archive**.

5. On the **Archive** tab, note that the archive mailboxes for all users other than Holly Dickson have a status of **Enabled**. These archive mailboxes were enabled when the VM lab environment was built for this training course and these users were preconfigured in the tenant. However, since you added Holly's user account in one of the first labs at the start of this course, her archive mailbox is **Disabled** by default. <br/>

	To enable Holly’s archive mailbox, select the check box next to **Holly Dickson** in the user list and then select **Enable Archive** in the menu bar that appears above the list of users.

6. In the **Warning** dialog box that appears, select **Enable** to confirm this action.

7. If necessary, select the **Refresh** icon on the menu bar above the list of users. Holly's archive mailbox should now be **Enabled**.

8. In your Microsoft Edge browser, leave your Edge browser and all its tabs open for the next task. 
 

### Task 2 – Create a retention policy for test user mailboxes

As part of your pilot project for Adatum, you will configure data retention through the Microsoft Purview portal by creating a new retention policy. You will then assign this retention policy to Joni Sherman and Lynne Robbins’ mailboxes. Joni and Lynne are Holly's two test users for compliance testing.

1. On LON-CL1, your Microsoft Edge browser should still have the Microsoft Purview portal open from the prior task.

2. In the **Microsoft Purview** portal, in the left-hand navigation pane, select **Data lifecycle management**, and then select **Microsoft 365**.

3. In the **Data lifecycle management** window, in the list of tabs that appear across the top of the page, select **Retention policies**.

4. On the **Retention policies** tab, select **+New retention policy** on the menu bar. This initiates the **Create retention policy** wizard.

5. On the **Name your retention policy** page, enter **Test user email retention** in the **Name** field and then select **Next**.

6. On the **Choose the type of retention policy to create** field, select **Static** and then select **Next**.

7. On the **Choose locations to apply the policy** page, note the Exchnage email location. It's currently set to include **All recipients**. You want to change this to just apply to Joni Sherman and Lynne Robbins' mailboxes. Under **All recipients**, select **Edit**.

8. In the **Exchange email** pane that appears, hover your mouse over **Joni Sherman** and then select her check box. Do the same for **Lynne Robins**. <br/>

	**Note:** If you select a user's name, the other check boxes that have been selected will be unselected. To select multiple users, you must hover your mouse over each user's name and select their check box that appears. <br/>

	Once both check boxes are selected, select **Done**.

9. On the **Choose locations to apply the policy** page, the **Exchange email** location should now indicate that **2 recipients** are included. <br/>

	Since this policy will only apply to Exchange email for Joni and Lynne, set the **Status** toggle switch to **Off** for all other locations in which it's currently set to On (**SharePoint sites**, **OneDrive accounts**, and **Microsoft 365 Groups**). Select **Next**.

10. On the **Decide if you want to retain content, delete it, or both** page, verify the **Retain items for a specific period** option is selected (if necessary, select it now). Then enter the following information for this option: <br/>

	- Retain items for a specific period - select in this field, and in the drop-down menu that appears, select **Custom**. Three fields will appear - years, months, and days. For testing purposes, Holly want to test email retention immediately and not wait a matter of months or years. As such, set the time periods to the following values: **Years - 0, Months - 0, Days - 3**.

	- Start the retention period based on - **When items were created**

	- At the end of the retention period - **Delete items automatically**

11. Select **Next**.

12. On the **Review and finish** page, review your selections. If anything needs to be changed, select the appropriate Edit link and make the necessary changes. Otherwise, if everything is correct, select **Submit**.

13. On the **You successfully created a retention policy** window, select **Done**.

14. Leave the **Data lifecycle management** tab open in your Edge browser as you will create another retentio policy in the next task.


### Task 3 – Create a retention policy to retain emails for all users

Once testing has concluded, Holly wants to preserve the content of all Exchange Online mailboxes from deletion for 5 years after the last modification. You must create a retention policy with this setting.

1. On LON-CL1, your Microsoft Edge browser should still have the Microsoft Purview portal open from the prior task, and it should be displaying the **Data lifecycle management** window.

3. In the **Data lifecycle management** window, in the list of tabs that appear across the top of the page, select **Retention policies**.

4. On the **Retention policies** tab, select **+New retention policy** on the menu bar. This initiates the **Create retention policy** wizard.

5. On the **Name your retention policy** page, enter **Exchange preservation** in the **Name** field and then select **Next**.

6. On the **Choose the type of retention policy to create** field, select **Static** and then select **Next**.

7. On the **Choose locations to apply the policy** page, note the Exchnage email location. It's currently set to include **All recipients**. Do not change this value, since you want this policy to apply to all user mailboxes.

8. Since this policy will only apply to Exchange email, set the **Status** toggle switch to **Off** for all other locations that are turned On. Select **Next**.

9. On the **Decide if you want to retain content, delete it, or both** page, verify the **Retain items for a specific period** option is selected (if necessary, select it now). Then enter the following information for this option: <br/>

	- Retain items for a specific period - **5 years**

	- Start the retention period based on - **When items were last modified**

	- At the end of the retention period - **Delete items automatically**

10. Select **Next**.

11. On the **Review and finish** page, review your selections. If anything needs to be changed, select the appropriate Edit link and make the necessary changes. Otherwise, if everything is correct, select **Submit**.

12. On the **You successfully created a retention policy** window, select **Done**.

13. In your Microsoft Edge browser, close all tabs except for the **Microsoft Office Home** tab and the tab containing the **Microsoft 365 admin center**.

You have now created a new retention policy in the Microsoft Purview portal that retains all Exchange emails from all mailboxes for 5 years after the last modification.

 # Proceed to Lab 4 - Exercise 3
 
