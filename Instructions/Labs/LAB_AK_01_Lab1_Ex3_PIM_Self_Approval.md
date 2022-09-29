# Learning Path 1 - Lab 1 - Exercise 3 - PIM Self-Approval

Since taking on her role as Enterprise Administrator, Holly Dickson has been inundated with user support requests. Because Holly does not have the bandwidth to respond to the requests in a timely manner, she wants Alex Wilber and Joni Sherman to begin responding to these requests. This will require that Alex and Joni have Helpdesk Administrator role permissions.  However, Holly does not want to permanently assign this role to Alex and Joni, since this is not their regular role, and she doesn't want this role to impact other services. Holly also doesn't want Alex and Joni to submit approval requests each time they need to be assigned the Helpdesk Admin role.

Instead, Holly wants to take advantage of the Privileged Identity Management (PIM) feature that enables users to self-activate an Azure AD role on an as-needed basis. Instead of requiring a Global admin (such as Holly) or a Privileged Role Administrator to assign a role to multiple people individually, PIM enables an organization to create a security group and then enable the group to be eligible for that specific role. When people are assigned as members of the group, they indirectly become eligible to be assigned the role. Holly wants to employ this feature at Adatum by creating a security group of eligible users (Alex and Joni) for the Helpdesk admin role. 

Once Alex and Joni are made eligible for this role, whenever they must respond to a user request, they will activate, or self-approve the role assignment. Alex and Joni can request to activate the role when they need its privileges, at which time they will have administrator control for a predetermined time period. 

Holly, on the other hand, simply wants to be notified whenever Alex or Joni self-approve the role. PIM lets you know when important events occur in your Azure Active Directory organization, such as when a role is assigned or activated. PIM keeps you informed by sending you and other participants email notifications. These emails may also include links to relevant tasks, such activating or renewing a role.


### Task 1 - Configure the Global Administrator role to require approval

Since the Microsoft 365 Global Administrator role provides a user with basically unlimited access to all Microsoft 365 resources, the number of users assigned to this role should obviously be kept to a minimum for security purposes. 

For the purpose of this lab, the lab hosting provider assigned the Global admin role to the MOD Administrator and three of the other predefined user accounts. After you added Holly as a Global admin, five of 12 user accounts in your tenant are now global admins, which is not something you would see in a real-world deployment. That being said, keep this guideline in mind for your real-world Microsoft 365 deployments. The best practice guideline that you should follow is to have from two to four Global admins.

Holly Dickson, Adatum's Enterprise Administrator, wants to limit access to Global admin role using Privileged Identity Management. To do so, she must first configure the role to require approval before it can be assigned as an eligible role for a user, and then she wants to assign herself as the approver whenever an eligible user requests activating the role.

Holly also wants to update the notification settings for the Global admin role. Privileged Identity Management (PIM) lets you know when important events occur in your Azure Active Directory (Azure AD) organization, such as when a role is assigned or activated. PIM keeps you informed by sending you and other participants email notifications. These emails might also include links to relevant tasks, such activating or renewing a role. In this task, Holly wants to update the notifications to ensure that approvals are tracked in real-time in a proactive manner.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as Holly Dickson from the previous lab exercise.

2. In your browser, select the **Microsoft 365 admin center** tab. In the left-hand navigation pane under the **Admin centers** section, select **Azure Active Directory**

3. In the **Azure Active Directory admin center**, in the left-hand navigation pane, select **All services**.

4. In the **All services** window, the services are separated into three sections - General, Identity, and Services. Under the **Security** section, select **Azure AD Privileged Identity Management**.

5. In the **Privileged Identity Management | Quick start** window, note how the window is divided into three parts - the navigation pane on the left, the middle pane (which provides navigation options for this page), and the detail pane on the right. <br/>

    In the middle pane under the **Manage** section, select **Azure AD roles**.

6. In the **Adatum Corporation | Quick start** window, in the middle pane under the **Manage** section, select **Settings**. 

7. In the **Adatum Corporation | Settings** window, select the **Global Administrator** role.

8. In the **Role setting details -  Global Administrator** window, select **Edit** on the menu bar at the top of the page.

9. In the **Edit role setting - Global Administrator** window, the **Activation** tab is displayed by default. In this tab, select the **Require Approval to activate** check box. 

10. In the **Select approver(s)** section, no specific approver has been selected. Holly wants to assign herself as the approver for this role, so select this section. In the **Select a member** pane that opens on the right, scroll down through the list of users and select **Holly Dickson**, and then select the **Select** button.

11. In the **Edit role setting - Global Administrator** window, select the **Notification** tab.

12. On the **Notification** tab, note the three activities that can trigger sending of notifications: **Send notifications when...**    <br/>

    - members are assigned as eligible to this role
    - members are assigned as active to this role
    - eligible members activate this role

    For each activity, a **Role assignment alert** can be sent. Beside sending this alert notification email to the default admin, Holly wants the **Role assignment alert** sent to the MOD administrator account. <br/>

    In the **Additional recipients** field for each of the three instances of the **Role assignment alert**, enter the MOD administrator's email ID of **admin@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider).

13. At the bottom of the **Edit role setting - Global Administrator** window, select **Update**.

14. Leave all browser tabs open for the next task.


### Task 1 - Create an eligible group for the Helpdesk Admin role

In the prior lab exercise, Holly Dickson limited access to Global admin role using Privileged Identity Management. To do so, she first configured the role to require approval before it could be assigned as an eligible role for a user, and then she assigned herself as the approver whenever an eligible user requested activating the role. 

For this next test of PIM in Adatum's pilot project, Holly has selected Alex Wilber and Joni Sherman to be eligible for the Helpdesk admin role. However, to simplify future role assignments, Holly wants to create a security group, assign Alex and Joni to the group, and then assign the group to the Helpdesk admin role. Holly will then enable the group to be eligible for the Helpdesk admin role.

Holly also wants to update the notification settings for the Helpdesk admin role. She wants to be notified whenever Alex or Joni self-approve the role. This will enable her to ensure that self-approvals are tracked in real-time in a proactive manner.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as Holly Dickson.

2. In your browser, select the **Microsoft 365 admin center** tab. In the left-hand navigation pane under the **Admin centers** section, select **Azure Active Directory**

3. In the **Azure Active Directory admin center**, in the left-hand navigation pane, select **All services**.

4. In the **All services** window, the services are separated into the following sections - General, Identity, Services, and Hybrid + multicloud. Under the **Identity** section, select **Groups**.

5. In the **Groups | All groups** window, select **New group** in the menu bar.

6. In the **New group** window, enter the following information:

    - Group type - **Security**

    - Group name - **PIM-Helpdesk-Administrators**

    - Group description - **Group of eligible users who can be assigned to the Helpdesk Administrator role in PIM**

    - Azure AD roles can be assigned to the group - **Yes**

    - Membership type - **Assigned**

    - Owners - Select **No owners selected**. In the **Add owners** pane, select **Holly Dickson** and then select the **Select** button.

    - Members - Select **No members selected**. In the **Add members** pane, select **Alex Wilber** and **Joni Sherman** and then select the **Select** button.

7. In the **New group** window, select **Create**.

8. A dialog box appears that says: **Creating a group to which Azure AD roles can be assigned is a setting that cannot be changed later. Are you sure that you want to add this capability?**. Select **Yes**.

9. On the **Groups | All groups** window, if the **PIM-Helpdesk-Administrators** group does not appear, select **Refresh** on the menu bar.

10 You must now make the **PIM-Helpdesk-Administrators** group eligible for role assignment. In the **Azure Active Directory admin center** navigation pane, select **All services**.

11. In the **All services** window, in the **Security** section, select **Azure AD Privileged Identity Management** (this feature also appears in the Identity section, so you can actually select either instance).

12. In the **Privileged Identity Management | Quick start** window, in the middle pane under the **Manage** section, select **Azure AD roles**.

13. In the **Adatum Corporation | Quick start** window, the detail pane on the right displays the **Privileged Identity Management** window. This window displays the following sections - Assign, Activate, Approve, and Audit. Under the **Assign** section, select **Assign Eligibility**.

14. In the **Adatum Corporation | Roles** window, scroll down through the list of roles and select **Helpdesk Administrator**.

15. In the **Helpdesk Administrator | Assignments** window, select **+Add assignments** on the menu bar. 

16. In the **Add assignments** window, the **Membership** tab is displayed by default. Under **Select member(s)**, select **No member selected**.

17. In the **Select a member** pane that appears on the right, enter **PIM** in the **Search** field. This will display the list of eligible users and groups whose name starts with **PIM**. Select the **PIM-Helpdesk-Administrators** group that appears, and then select the **Select** button.

18. In the **Add assignments** window, select **Next** (this does the same thing as selecting the **Setting** tab). 

19. In the **Add assignments** window, under the **Settings** tab, verify the **Assignment type** option is set to **Eligible**. Also verify the **Permanently eligible** check box is selected (if not, then do so now), and then select **Assign**. 

20. In the **Global Administrator | Assignments** window, note that the **PIM-Helpdesk-Administrators** group is an eligible assignment to the Helpdesk Administrator role. Because **PIM-Helpdesk-Administrators** is a group, it means that all members of this group (which consists of Alex Wilber and Joni Sherman) are now eligible to be assigned the Helpdesk Administrator role.

    **Note:** Lab testing has shown that it can sometimes take up to 30 minutes for new assignments to appear under the **Eligible assignments** tab. If **PIM-Helpdesk-Administrators** doesn't appear immediately, wait a few minutes and then select the **Refresh** option on the menu bar. Continue to select the **Refresh** option every few minutes until **PIM-Helpdesk-Administrators** appears in the list of **Eligible assignments**.

21. Leave all browser tabs open for the next task.


### Task 3 - Submit a request for the Global Admin role

Now that the **PIM-Global-Administrators** group has been made eligible for the Global administrator role, the members of the group (in this case, Patti Fernandez) can be assigned the Global Admimistrator role using the Azure AD Privileged Identity Management solution. Holly wants to test out the PIM process in her pilot project. In this task, you will take on the role of Patti, who will submit a request to be assigned Global administrator role privileges. In the next task, Holly will review her request and approve it.

**Note:** The activation request process is set up to require Multi-Factor Authentication (MFA). If you do not have a phone to complete this process, notify your instructor. You may be able to partner up with another student to watch them complete the remaining two tasks.

1.  In LON-CL1, right-click on the **Edge** icon on the taskbar and in the menu that appears, select **New InPrivate window**. 

2. In your InPrivate browser session, enter the following URL in the address bar: **https://portal.azure.com**

3. You're now going to log into Azure as Patti Fernandez. In the **Sign in** window, enter **PattiF@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**. In the **Enter password** window, enter **User.pw1** and then select **Sign in**. In the **Stay signed in?** dialog box, select the **Don't show this again** check box and then select **Yes**.

4. In the **Welcome to Microsoft Azure** dialog box that appears, select **Maybe later** to skip the tour.

5. In the **Microsoft Azure** portal, in the **Azure services** section, and then on the right side of the section, select **More services**. This opens the **All services** window.

6. In the **All services** window, enter **priv** in the **Search** box at the top of the page. In the list of search results, select **Azure AD Privileged Identity Management**.

7. In the **Privileged Identity Management | Quick start** window, in the **Tasks** section in the left-hand navigation pane, select **My Roles**.

8. In the **My roles | Azure AD roles** window, the **Eligible assignments** tab is displayed by default. Remember, in the prior task Holly assigned Patti as a member of the **PIM-Global-Admiistrators** group, which Holly later assigned as an eligible group for the Global Administrator role. As such, this role appears in the list of **Eligible assignments**. Under the **Action** column for the Global Administrator role, select **Activate**.

9. In the **Activate - Global Administrator** pane, a warning message is displayed at the top of the pane indicating additional verification is required. Select this message, which is hyperlinked.

10. In the **More information required** window that appears, select **Next**. 

11. In the **Enter password** window, enter **User.pw1** in the **Password** field and then select **Sign in**.

12. On the **Microsoft Authenticator** page, you can download this mobile app or use a different method for MFA verification. For the purposes of this lab, we recommend you use your mobile phone so that you do not have to take time installing the Microsoft Authenticator app that you may not use again after this training class. Select the **I want to set up a different method** option at the bottom of the page. 

13. On the **Choose a different method** dialog box that appears, select the drop-down arrow in the **Which method would you like to use?** field, select **Phone**, and then select **Confirm**. 

14. In the **Phone** window that appears, under **What phone number would you like to use?** field, select your country or region, and then in the field next to it, enter your phone number (in the format **nnn-nnn-nnnn**). Verify the **Text me a code** option is selected and then select **Next**.

15. Retrieve the verification code from the text message that is sent to your phone.

16. In the **Phone** window, enter the 6 digit verification code in the **Enter code** field and then select **Next**.

17. Once verification is complete and you receive a message indicating your phone was registered successfully, select **Next**.

18. On the **Success!** page, select **Done**.

19. If you receive a dialog box indicating your sign in has timed out, you will have to enter Patti's password of **User.pw1** and then you will be sent another verification code to your phone. On the **Enter code** window, enter this new code and then select **Verify**. 

20. If you take too long to complete this process, the **Enter password** window will appear with a message indicating you took too long to complete the sign in process, so you will be timed-out. If this occurs, you must sign in again with Holly's password of **User.pw1**. Another verification code will be texted to your phone, so enter it in the **Enter code** screen that appears and select **Verify**.

21. In the **Activate - Global Administrator** pane that appears on the right-side of the screen, enter **Testing PIM** in the **Reason** field, and then select the **Activate** button at the bottom of the pane.

22. On the **My roles | Azure AD roles** window, the **Eligible assignments** tab is displayed on the menu bar. Select the **Active assignments** tab that appears next to it. Note that no roles appear. <br/>

     **Note:** If you recall, back in Task 1 Holly set up the Global Administrator role so that activation to a user account will require approval. What Patti just did was request that the Global Admin role be activated for her user account. This will send a request to Holly, who can then either approve or deny Patti's request for role activation. Holly will review this request in the next task.

23. Leave the InPrivate browser session open. You will return to it in the next task once Holly approves Patti's request.


### Task 4 -  Approve the request for the Global Admin role

Back in Task 1, Holly set herself up as the approver for the Global Administrator role. Since Patti has submitted a request to be assigned this role, Holly must review the request and determine whether to accept or deny it. 

1.  In LON-CL1, select the Edge icon on your taskbar to see windows for the two Edge sessions that you have open - the window on the left is the original Edge browser session in which you are signed into **Microsoft 365** as **Holly Dickson**, and the window on the right is the InPrivate Browser session in which you are signed into **Azure AD** as **Patti Fernandez**. <br/>

    Select the window on the left to go back to the original Edge browser session in which you are signed in as **Holly Dickson**. 

2.  In your browser, select the **Global Administrator | Assignments** tab. This should display the **Global Administrator | Assignments** window in the **Azure Active Directory admin center**. <br/>

    In the navigation thread at the top of the page (**All services > Privileged Identity Management > Adatum Corporation**, select **Privileged Identity Management**.

3. In the **Privileged Identity Management | Quick start** window, in the middle pane under **Tasks**, select **Approve requests**.

4. In the **Approve requests | Azure AD roles** window, in the **Requests for role activations** section, select the check box to the left of the Global Administrator request from Patti Fernandez, and then select the **Approve** button.

5. In the **Approve Request** pane that appears on the right-side of the screen, enter **PIM testing** in the **Justification** field and then select **Confirm**.

6.  Select the **Edge** icon on the taskbar and switch back to the InPrivate browser session where Patti is signed in. In the **My roles | Azure AD roles** window that should still be displayed, the **Active assignments** tab is currently selected from the prior task, prior to approving Patti's request. Select **Refresh** on the menu bar. Note how the Global Administrator role is now activated for Patti. </br/>

    You have just verified that Patti has been assigned the Global Administrator role using the Azure AD Privileged Identity Management solution.

7. Close the InPrivate browser session.

8. In your Edge browser session, close all the tabs except for the **Microsoft Office Home** tab and the **Microsoft 365 admin center** tab. Leave these two tabs open for the next lab.


# Proceed to Lab 1 - Exercise 4
