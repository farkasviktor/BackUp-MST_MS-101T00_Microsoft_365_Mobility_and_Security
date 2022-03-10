# Module 10 - Lab 9 - Exercise 1 - Enable Device Management

In your role as Holly Dickson, Adatum's Enterprise Administrator, you have Microsoft 365 deployed in a virtualized lab environment for your pilot project. In this lab, you will manage user devices using Intune.

In this exercise you will verify that Adatum has installed the Enterprise Mobility + Security E5 product. You will then verify that it has been assigned to your test user accounts, and you will assign a license to yourself. You will then enable device management with Intune.

### Task 1: Verify and assign Enterprise Mobility + Security licenses

In this task you will verify that Adatum has installed the Enterprise Mobility + Security E5 product and you will check how many licenses are available. You will then verify that a license has been assigned to your test user accounts, and you will assign a license to yourself.

1. Switch to LON-CL1, where you should still be logged in as the **Admin** account and into Microsoft 365 as Holly Dickson. 

2. In **Microsoft Edge**, you should still have a tab open for the **Microsoft 365 admin center**; if so, select that tab now. If not, enter **https://portal.office.com**, sign in as **Holly**, select the **App launcher** icon (the square made up of 3 rows of dots) that appears above the **Home** icon in the top left corner of the screen, and then in the **Apps** pane that appears, select **Admin**; this opens the **Microsoft 365 admin center** in a new browser tab.

3. In the **Microsoft 365 admin center**, select **Billing** in the left-hand navigation pane, and then under it, select **Licenses**.

4. On the **Licenses** page, note the number of licenses that are available with your tenant and the number that have already been assigned to user accounts for each of the available licenses. In your VM lab environment, 15 **Enterprise Mobility + Security E5** licenses were assigned to your tenant, and your lab hosting provider already assigned a license to the 10 pre-existing user accounts. <br/>

   Note how the **Office 365 E5** license also has 15 available with your tenant, but in this case, 11 of the 15 have been assigned to users. Your lab hosting provider assigned a license to each of the 10 pre-existing user accounts, and when you created Holly Dickson's user account back in lab 1, you assigned her a license as well. You did not assign Holly an **Enterprise Mobility + Security E5** license. <br/>
   
   In the list of licenses, select **Enterprise Mobility + Security E5**.

5. In the **Enterprise Mobility + Security E5** page, under the list of users, verify that all 10 of the pre-existing user accounts provided by your lab hosting provider have been assigned a license. <br/>

   The one user who was not assigned an **Enterprise Mobility + Security E5** license is Adatum's Enterprise Administrator, Holly Dickson. When you created Holly's user account back in Lab 1, you were instructed at that time to only assign her an Office 365 E5 license. You will now assign her an Enterprise Mobility + Security E5 license. <br/>

    To assign Holly a license, select **+Assign licenses**, which appears in the menu bar above the list of users.

6. In the **Assign licenses to users** pane, select the **Enter a name or email address** field, and in the list of users that appears, select **Holly Dickson**, and then select the **Assign** button at the bottom of the pane.

7. Close the **You assigned a license to Holly Dickson** window.

8. Leave all browser tabs open for the next task.

You have now verified the available Enterprise Mobility + Security E5 licenses in your tenant and assigned an EMS E5 license to Holly.


### Task 2: Enable device management with Intune

Devices must be managed before you can give users access to company resources or manage settings on those devices. This begins with enabling device management with Intune. With Adatum's tenant, Holly will discover that Intune has been set by default as Adatum's MDM authority.

1. You should still be logged into LON-CL1 as the **Admin** account and into Microsoft 365 as Holly Dickson.

2. In the **Microsoft 365 admin center**, in the left-hand navigation pane under the **Admin centers** group, select **Endpoint Manager**.

3. In the **Microsoft Endpoint Manager admin center**, select **Devices** in the left-hand navigation pane.

4. In the **Devices | Overview** page, the **Enrollment status** tab is displayed by default. By default, Intune has been set as Adatum's MDM authority. <br/>

   In the middle pane under the **Policy** section, select **Compliance policies**. Even though no data is currently available, review the information on the **Compliance policies | Policies** page regarding device management.

5. Select the **Back arrow** on the address bar to return to the **Devices | Overview** page. In the middle pane under the **Policy** section, select **Conditional Access**. Review the information on the **Conditional Access | Policies** page.

6. Select the **Back arrow** on the address bar to return to the **Devices | Overview** page. In the middle pane under the **Policy** section, select **Enrollment restrictions**. Review the information on the **Devices | Enrollment restrictions** page.

7. Select the **Back arrow** on the address bar to return to the **Devices | Overview** page. In the middle pane under the **Policy** section, select **Configuration profiles**. Review the information on the **Devices | Configuration profiles** page.

8. Select the **Back arrow** on the address bar to return to the **Devices | Overview** page. 

9. In your Edge browser, leave all the tabs open for the next lab exercise. 

You have now verified that Intune is the default MDM solution for your tenant.


# Proceed to Lab 9 - Exercise 2
