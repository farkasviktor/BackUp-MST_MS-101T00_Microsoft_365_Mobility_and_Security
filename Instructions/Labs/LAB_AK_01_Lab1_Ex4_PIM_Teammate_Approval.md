# Learning Path 1 - Lab 1 - Exercise 4 - PIM Teammate Approval Request

Up to this point, you have conducted two forms of PIM approval:

- one by an administrator (Holly), who approved the activation and assignment of the Global Administrator role to Patti Fernandez.
- another by Alex Wilber, who self-approved the assignment of the Helpdesk administrator role to his user account. 

In this exercise, you will conduct a third form a PIM approval, which is having a user (non-admin) approve the assignment of a role to another user. 

In an attempt to decrease overhead but still maintain a secure way of managing administrator roles, Holly decided to allow Alex Wilber and Joni Sherman approve each other’s request to activate the Intune Administrator role.  This will allow Alex and Joni to perform tasks within Intune without having to wait for Holly to approve their requests. 


### Task 1 - Configure the Intune Administrator role to require approval

For this final test of PIM in Adatum's pilot project, Holly has selected Alex Wilber and Joni Sherman to be eligible for the Intune admin role. To simplify future role assignments, Holly wants to create a security group, assign Alex and Joni to the group, and then assign the group to the Intune admin role - just as she previously did in the prior lab exercise for the Helpdesk administrator role. 

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as Holly Dickson.

2. In your Edge browser, select the tab containing the **Azure Active Directory admin center**, which should still be open from the prior lab exercise. 

3. In the **Azure Active Directory admin center**, in the left-hand navigation pane, select **All services**.

4. In the **All services** window, under the **Identity** section, select **Groups**.

5. In the **Groups | All groups** window, select **New group** in the menu bar.

6. In the **New group** window, enter the following information:

    - Group type - **Security**

    - Group name - **PIM-Intune-Administrators**

    - Group description - **Group of eligible users who can be assigned to the Intune Administrator role in PIM**

    - Azure AD roles can be assigned to the group - **Yes**

    - Membership type - **Assigned**

    - Owners - Select **No owners selected**. In the **Add owners** pane, select **Holly Dickson**.

    - Members - Select **No members selected**. In the **Add members** pane, select **Alex Wilber** and **Joni Sherman**

7. In the **New group** window, select **Create**.

8. A dialog box appears that says: **Creating a group to which Azure AD roles can be assigned is a setting that cannot be changed later. Are you sure that you want to add this capability?**. Select **Yes**.

9. On the **Groups | All groups** window, if the **PIM-Intune-Administrators** group does not appear, select **Refresh** on the menu bar.

10 You must now make the **PIM-Intune-Administrators** group eligible for role assignment. In the **Azure Active Directory admin center** navigation pane, select **All services**.

11. In the **All services** window, in either the **Identity** or **Security** sections, select **Azure AD Privileged Identity Management**.

12. In the **Privileged Identity Management | Quick start** window, in the middle pane under the **Manage** section, select **Azure AD roles**.

13. In the **Adatum Corporation | Quick start** window, under the **Assign** section, select **Assign Eligibility**.

14. In the **Adatum Corporation | Roles** window, scroll down through the list of roles and select **Intune Administrator**.

15. In the **Helpdesk Administrator | Assignments** window, select **+Add assignments** on the menu bar. 

16. In the **Add assignments** window, the **Membership** tab is displayed by default. Under **Select member(s)**, select **No member selected**.

17. In the **Select a member** pane that appears on the right, enter **PIM** in the **Search** field. This will display the list of eligible users and groups whose name starts with **PIM**. Select the **PIM-Intune-Administrators** group that appears, and then select the **Select** button.

18. In the **Add assignments** window, select **Next** (this does the same thing as selecting the **Setting** tab). 

19. In the **Add assignments** window, under the **Settings** tab, verify the **Assignment type** option is set to **Eligible**. Also verify the **Permanently eligible** check box is selected (if not, then do so now), and then select **Assign**. 

20. In the **Helpdesk Administrator | Assignments** window, note that the **PIM-Intune-Administrators** group is an eligible assignment to the Intune Administrator role. Because **PIM-Intune-Administrators** is a group, it means that all members of this group (which consists of Alex Wilber and Joni Sherman) are now eligible to be assigned the Intune Administrator role.

    **Note:** Lab testing has shown that it can sometimes take up to 30 minutes for new assignments to appear under the **Eligible assignments** tab. If **PIM-Intune-Administrators** doesn't appear immediately, wait a few minutes and then select the **Refresh** option on the menu bar. Continue to select the **Refresh** option every few minutes until **PIM-Intune-Administrators** appears in the list of **Eligible assignments**.

21. Leave all browser tabs open for the next task.


### Task 2 - Assign an eligible group to the Intune Admin role

In this exercise, Holly will enable the PIM-Intune-Administrators group to be eligible for the Intune admin role. However, not only will Holly make the group eligible for the role, but she will also make its members approvers of the role requests. Holly will then configure the role so that PIM notifies her of all approvals for this role.

As in the prior PIM exercise involving the Helpdesk admin role, Holly is trusting that Alex and Joni won't activate the Intune admin role unless they're required to do. Therefore, Holly will only require that Alex and Joni provide a justification whenever they must activate the role. In addition, Holly wants to configure the role so that Alex and Joni can approve each other's request for role activation. Holly simply wants to be notified whenever either user approves a request from the other.

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as Holly Dickson from the previous lab exercise.

2. In your browser, you should still have the **Azure Active Directory admin center** open from the prior task. In the left-hand navigation pane, select **All services**.

3. In the **All services** window, under the **Security** section, select **Azure AD Privileged Identity Management**.

4. In the **Privileged Identity Management | Quick start** window, in the middle pane under the **Manage** section, select **Azure AD roles**.

5. In the **Adatum Corporation | Quick start** window, in the middle pane under the **Manage** section, select **Settings**. 

6. In the **Adatum Corporation | Settings** window, select the **Intune Administrator** role.

7. In the **Role setting details -  Intune Administrator** window, select **Edit** on the menu bar at the top of the page.

8. In the **Edit role setting - Intune Administrator** window, the **Activation** tab is displayed by default. Un-check (clear) the **Require justification on activation** check box. Holly knows that Alex and Joni will only activate the role when needed, so she doesn't require a justification from them to activate the role assignment (however, in the next step, Holly will require justification when they request assignment of the role).

10. You're currently in the **Activation** tab. Select the **Assignment** tab that appears next to it. Verify the **Require justification on active assignment** check box is selected (if not, select it now).

11. In the **Edit role setting - Intune Administrator** window, select the **Notification** tab.

12. On the **Notification** tab, under the **Send notifications when eligible members activate this role** section, Holly wants to be notified when Alex or Joni approve this role. Therefore:

    - Verify the **Role activation alert** check box is selected.
    - The default recipient for the **Role activation alert** is **Admin**. This refers to the Global Administrators (Holly) and any Privileged Role Administrators. 
    - Un-check (clear) the **Notification to activated user (requestor)**. Since Alex and Joni will be approving each other's requests, they don't need to receive a notification when they do so.

13. At the bottom of the **Edit role setting - Intune Administrator** window, select **Update**.

14. Leave all browser tabs open for the next task.


### Task 3 - Submit a request for the Intune Admin role

At this point in Holly's pilot project, the **PIM-Intune-Administrators** group has been made eligible for the Intune administrator role. The members of the group (in this case, Alex Wilber and Joni Sherman) can now be assigned the Intune Admimistrator role using the Azure AD Privileged Identity Management solution. Holly wants to test out the PIM process in her pilot project. In this task, you will take on the role of Joni Sherman, who will submit a request to approve assigning the Intune Administrator role to her account. 

1.  In LON-CL1, right-click on the **Edge** icon on the taskbar and in the menu that appears, select **New InPrivate window**. 

2. In your InPrivate browser session, enter the following URL in the address bar: **https://portal.azure.com**

3. You're now going to log into Azure as Joni Sherman. In the **Sign in** window, enter **JoniS@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**. In the **Enter password** window, enter **User.pw1** and then select **Sign in**. In the **Stay signed in?** dialog box, select the **Don't show this again** check box and then select **Yes**.

4. In the **Welcome to Microsoft Azure** dialog box that appears, select **Maybe later** to skip the tour.

5. In the **Microsoft Azure** portal, in the **Azure services** section, and then on the right side of the section, select **More services**. This opens the **All services** window.

6. In the **All services** window, enter **priv** in the **Search** box at the top of the page. In the list of search results, select **Azure AD Privileged Identity Management**.

7. In the **Privileged Identity Management | Quick start** window, in the **Tasks** section in the left-hand navigation pane, select **My Roles**.

8. In the **My roles | Azure AD roles** window, the **Eligible assignments** tab is displayed by default. Remember, in the prior task Holly assigned Joni and Alex as members of the **PIM-Intune-Admiistrators** group, which Holly later assigned as an eligible group for the Intune Administrator role. As such, this role appears in the list of **Eligible assignments** for Joni. Under the **Action** column for the Intune Administrator role, select **Activate**.

9. In the **Activate - Intune Administrator** pane that appears on the right-side of the screen, enter **Device management support requests from various users that require resolution** in the **Reason** field, and then select the **Activate** button at the bottom of the pane.

10. On the **My roles | Azure AD roles** window, the **Eligible assignments** tab is displayed on the menu bar. Select the **Active assignments** tab that appears next to it. Note that no roles appear. <br/>

     **Note:** If you recall, back in Task 1 Holly set up the Intune Administrator role so that activation to a user account will require approval. What Joni just did was request that the Intune Admin role be activated for her user account. This will send a request to Alex, who can then either approve or deny Joni's request for role activation. Alex will review this request in the next task.

11. Close the InPrivate browser session.


### Task 4 -  Approve the request for the Intune Admin role

Back in Task 1, Holly assigned the PIM-Intune-Administrators group as approver for the Intune Administrator role. This means that both Joni and Alex, as members of the group, can approve requests for role assignment. Since Joni submitted a role assignment request in the prior task, Alex must review the request and determine whether to accept or deny it. 

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


# End of Lab 1
