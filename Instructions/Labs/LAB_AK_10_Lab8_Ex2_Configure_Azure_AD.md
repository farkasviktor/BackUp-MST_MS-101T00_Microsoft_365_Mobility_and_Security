# Learning Path 10 - Lab 8 - Exercise 2 - Configure Azure AD for Intune 

In this exercise you will activate automatic client enrollment to Intune for Mobile Device Management (MDM) for all Windows 10 and later devices. This will enable you to manage mobile device access and set policies for restricting access to Windows 10 and later devices unless certain actions are adopted, such as strong passwords and screen timeouts.

### Task 1: Integrate Azure AD with Intune

1. You should still be logged into LON-CL1 as the local **Admin** account, and in your Edge browser, you should still be logged into Microsoft 365 as **Holly Dickson**.

2. In your browser, select the **Microsoft 365 admin center** tab, which should still be open; if not, navigate to **https://admin.microsoft.com.** 

3. In the **Microsoft 365 admin center**, in the left-hand navigation pane under **Admin centers**, select **Endpoint Manager**. This returns the **Microsoft Intune admin center**.

4. In the **Microsoft Intune admin center**, in the left-hand navigation pane, select **Devices**.

5. In the **Devices | Overview** page, in the middle pane under the **Device enrollment** section select **Enroll devices**.

6. In the **Enroll devices | Windows enrollment** page, under the **General** section, select **Automatic Enrollment**.

7. In the **Configure** window, there are two user scope settings - **MDM user scope** and **MAM user scope**. In the **MDM user scope** row, select **All**.<br/>

    **Note:** By setting this parameter to **All**, you are allowing all users who join their devices to Azure AD to automatically enroll them to Intune as well.

8. Below the list of MDM-related fields, select **Restore default MDM URLs** to ensure the correct URLs for client enrollment are configured.

9. In the menu bar at the top of the **Configure** window, select **Save**.

10. Leave all browser tabs open for the next task.

You have now configured your tenant so that all users can enroll their Windows 10 and 11 clients into Intune as soon they log into their devices with their Azure AD account credentials.


### Task 2: Configure Azure AD join

In this task, you will change the default settings for users to join their devices to Adatum's Azure AD tenant.

1. In your browser, select the **Microsoft 365 admin center** tab, which should still be open; if not, navigate to **https://admin.microsoft.com.** 

2. In the **Microsoft 365 admin center**, in the left-hand navigation pane under the **Admin centers** group, select **Azure Active Directory.** This returns the **Microsoft Entra admin center**.

3. In the **Microsoft Entra admin center**, in the left-hand navigation pane, select **Devices**, and then select **All devices**.

4. In the **Devices | All devices** window, in the details pane on the right, verify that **LON-CL2** is displayed in the list of devices. <br/>

   **Note:** Back in Lab 4, you performed a task that configured Mobile Device Management (MDM) auto-enrollment. When you performed this MDM configuration lab, it automatically enrolled the devices belonging to members of the Compliance Test Users group. At the time, Joni Sherman was logged into Microsoft 365 on LON-CL2, and since she was a member of the Compliance Test Users group, LON-CL2 was automatically enrolled into Intune as its MDM authority. <br/>

5. In the **Devices | All devices** window, in the middle pane, select **Device settings**.

6. In the **Devices | Device settings** window, in the **Users may join devices to Azure AD** option, verify that **All** is selected. This means that all Azure AD users can join their devices to Azure Active Directory.

7. Scroll down to the bottom of the window. Under **Local administrator settings**, no local administrators are displayed. Select the **Manage Additional local administrators on all Azure AD joined devices**. <br/>

   On the **Device Administrators | Assignments** window, note that no role assignments were found. In the next several steps, you will add a role assignment.

8. In the **Device Administrators | Assignments** window, select **+Add assignments** on the menu bar.

9. In the **Add assignments** pane on the right, select **Alex Wilber** in the list of users and then select the **Add** button at the bottom of the screen.

10. In the navigation thread that appears at the top of the screen (Home > Devices | Device settings > Device Administrators), select **Devices | Device settings**.

11. On the **Devices | Device settings** page, verify the **Require Multi-Factor Authentication to register or join devices with Azure AD** toggle switch is set to **No**. The **Maximum number of devices per user** is currently set to **50**; select this field and in the drop-down menu that appears, and then select **10**.

11. On the menu bar at the top of the page, select **Save**.

12. Leave all browser tabs open for the next task.

You have changed the default settings for users to join their devices to your Azure AD tenant.


### Task 3: Create dynamic Azure AD device group

In Azure Active Directory, you can use rules to determine group membership based on user or device properties. Dynamic membership is supported for security groups or Microsoft 365 groups. When a group membership rule is applied, user and device attributes are evaluated for matches with the membership rule. When an attribute changes for a user or device, all dynamic group rules in the organization are processed for membership changes. Users and devices are added or removed if they meet the conditions for a group. Devices can only be used in Security groups.

In this task, Holly wants to create a new Security group for enrolled devices within Adatum. This group will support dynamic membership when a device's management type is set to MDM.

1. In your browser, in the **Microsoft Entra admin center**, in the left-hand navigation pane, select **Groups** and then select **All groups**.

2. In the **Groups | All groups** window, in the details pane on the right, select **New group** on the menu bar.

3. In the **New Group** window, enter the following information:

    - Group type: **Security**
    - Group name: **Enrolled Devices**
    - Membership type: **Dynamic Device**
    - Owner: select **No owners selected**, then in the **Add Owners** window, select **Alex Wilber** and then select the **Select** button
    
4. At the bottom of the **New Group** window, under **Dynamic device members**, select **Add dynamic query**.

5. In the **Dynamic membership rules** window, configure the following fields for this expression:

    - Property: select the drop-down arrow and select **managementType**
    - Operator: select the drop-down arrow and select **Equals**  
    - Value: enter **MDM**

6. Select **+Add expression**. It should display the following in the **Rule syntax** field:<br/>

    **(device.managementType -eq  &quot;MDM&quot;)**

7. Select **Save** in the menu bar at the top of the window.

8. In the **New Group** window, select the **Create** button at the bottom of the window.

9. In the **Groups | All groups** window, the **Enrolled Devices** group should now appear in the list of groups. If the group does not appear, select the **Refresh** option on the menu bar. 

10. Leave all browser tabs open for the next task.


# Proceed to Lab 8 - Exercise 3
