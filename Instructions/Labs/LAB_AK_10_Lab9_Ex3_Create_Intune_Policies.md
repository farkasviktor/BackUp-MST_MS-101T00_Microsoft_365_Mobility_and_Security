# Module 10 - Lab 9 - Exercise 3 - Create Intune Policies 

Many mobile device management (MDM) solutions help protect organizational data by requiring users and devices to meet certain requirements. In Intune, these requirements are referred to as compliance policies. Compliance policies define the rules and settings that users and devices must meet to be compliant. When combined with Conditional Access requirements, administrators can block users and devices that do not meet the rules.

In this exercise, you will begin by creating a noncompliance notification message template. Then when you create a compliance policy that checks the Windows 10 and later devices to ensure they are running a minimum OS version of Windows, you will assign this email notification template to the policy. If a device is running a noncompliant version of Windows, the policy will be triggered, the device will be marked as noncompliant, an email will be sent to the end user notifying them of the situation. 

### Task 1: Create a noncompliant email message template

In your role as Holly Dickson, Adatum's Enterprise Administrator, want to send an email message to any end user whose Windows 10 or later device becomes noncompliant. Before you create a compliance policy in task 2, you must first create the noncompliance email message template that you will assign to the policy.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, you should still have the **Microsoft Endpoint Manager admin center** open from the first exercise in this lab; if so, then select it now. If you closed it, then in **Microsoft 365 admin center**, under the **Admin centers** group in the left-hand navigation pane, select **Endpoint Manager**. 

3. In the **Microsoft Endpoint Manager admin center**, in the left-hand navigation pane select **Endpoint security**.

4. On the **Endpoint security | Overview** page, the **Manage** section appears in the middle of the page's navigation pane. Under this section, select **Device compliance**.

5. On the **Compliance policies | Policies** page, in the navigation pane for this page, select **Notifications**. 

6. On the **Compliance policies | Notifications** page, select **+Create notification** on the menu bar. 

7. On the **Create notification** page, note the three steps that appear at the top of the page. You are currently on the step **1 - Basics** page. In the **Name** field, enter **Noncompliant OS version**. Leave all the other options set to their default settings and select **Next**.

8. On the step **2 - Notification message templates** page, select your appropriate **locale**, and then enter **WARNING: Noncompliant device** in the **Subject** field. Then enter the message **Your Windows 10 or later device is not running a compliant version of the OS. The device has been marked as noncompliant and is now locked.**, select the check box for **IsDefault**. Select **Next**.

9. On the step **3 - Review + create** page, review your template settings. If any need to be corrected, select **Previous** to return to the appropriate page and make the necessary edits. If everything looks correct, select **Create**.

10. In your browser session, leave all the tabs open for the next task.


### Task 2: Create and apply a compliance policy

In your role as Holly Dickson, Adatum's Enterprise Administrator, you will create a compliance policy that governs Windows 10 devices at Adatum Corporation. This policy will dictate what the minimum OS version that must be installed on a device in order for it to access Adatum's environment. It will also control how long a device can stay out of compliance before it's locked out from use, thereby, requiring administrator assistance to make it operational again. The policy will also control who it's assigned to, which in this case will be all devices enrolled in Microsoft Intune.

Given the problems caused at Adatum by devices that are running old versions of Windows, Holly wants to mark any device as noncompliant that is running a version of the OS that is older than version 10.0.17763.1192. Marking a device as noncompliant will lock the device. In the policy that Holly wants to create, any device running a version of Windows that is older than this version will be marked as noncompliant, and an email will be sent to the end-user notifying them of the situation.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, you should still have the **Microsoft Endpoint Manager admin center** open from the first exercise in this lab; if so, then select it now. If you closed it, then in **Microsoft 365 admin center**, under the **Admin centers** group in the left-hand navigation pane, select **Endpoint Manager**. 

3. In the **Microsoft Endpoint Manager admin center**, in the left-hand navigation pane select **Devices**. 

4. In the **Devices | Overview** page, the **Policy** section appears in the middle of the page's navigation pane. Under this section, select **Compliance policies**.

5. On the **Compliance policies | Policies** page, select **+Create Policy** on the menu bar.

6. On the **Create a policy** pane that appears, select the **Platform** field, and in the drop-down menu that appears, select **Windows 10 and later**. Select **Create**.

7. On the **Windows 10 compliance policy** window, note the five steps that appear at the top of the page. You are currently on the step **1 - Basics** page. Enter **Compliance1** in the **Name** field and then select **Next**.

8. On the step **2 - Compliance settings** page, select **Device Health** to expand it. Review the available settings and then select **Device Health** again to collapse it. 

9. On the step **2 - Compliance settings** page, select **Device Properties** to expand it. In the **Minimum OS version** field, enter **10.0.17763.1192** and then note the check mark that appears on the right side of the field. Select **Device Properties** again to collapse the section. 

10. On the step **2 - Compliance settings** page, expand the remaining sections and review them, and then when you are done, select **Next**.

11. On the step **3 - Actions for noncompliance** page, you can create a list of actions that you want taken when a device becomes noncompliant. One default action is already defined (**Mark device noncompliant**); this action cannot be changed or deleted. This action is scheduled to be performed **Immediately** (which means, on the day the device becomes noncompliant, which is 0 days after noncompliance). <br/>

    In addition to marking the device as noncompliant, Holly also wants to notify the end user with an email. In the **Action** column, under the **Mark device compliant** action, select the action field. In the drop-down arrow that appears, select **Send email to end user**. <br/>

    Leave the **Schedule (days after noncompliance)** field set to 0. <br/>
    
    Under the **Message template** column, select **None selected**. In the **Notification message templates** pane that appears, select **Noncompliant OS version** and then select the **Select** button. 
    
    **Note:** You will not send the email to any additional recipients. If you select **None selected** under the **Additional recipients** column, you will have to select an Azure AD group to send the email to (you cannot select an individual user). Other than the end user who owns the device, Holly does not want to notify any other group, so you will not define any additional recipients.
    
    **Note:** To the far right of the **Send email to end user** row is an ellipsis icon. If you select this icon, you can select the option to Delete this action if you decide you no longer want to include it in this policy. You want to send the email notification, so do not select this Delete option.
    
12. Select **Next**.

13. On the step **4 - Assignments** page, you want to assign this policy to all the devices in the **Enrolled devices** group, which you created in the prior exercise. <br/>

    In the **Assignments** tab under the **Included groups** section, select **Add groups**. In the **Select groups to include** pane that appears, select **Enrolled devices** and then select the **Select** button at the bottom of the pane. Select **Next**.

14. On the step **5 - Review + create** page, review the policy settings. If anything needs to be fixed, select **Previous** and make the necessary corrections. However, if everything looks correct, select **Create**.

15. In your **Edge** browser, select the **Azure Active Directory admin center** tab. If you closed this tab at the end of the prior exercise, then in the **Microsoft 365 admin center**, in the left-hand pane under **Admin centers**, select **Azure Active Directory**.

16. In the **Azure Active Directory admin center**, in the left-hand navigation pane, select **Azure Active Directory**.

17. In the **Adatum Corporation | Overview** window, the **Manage** section appears in the middle of the page's navigation pane. Under this section, select **Mobility (MDM and MAM).**

18. In the **Adatum Corporation | Mobility (MDM and MAM)** window, select **Microsoft Intune.**

19. In the **Configure** window, in the **MAM User scope** setting, select **All**.

20. Select **Save** in the menu bar at the top of the window, and then select the **X** in the upper right corner to close the **Configure** window.

21. Leave all browser tabs open for the next task.


### Task 3: Manually create an EFS DRA Certificate

EFS, which is the Encrypted File System that is built into Windows, allows anyone to encrypt a file. The encryption is done using digital certificates, and as part of that process, Windows assigns a Data Recovery Agent (DRA). A data recovery agent is a Microsoft Windows user who has been granted the right to decrypt data that was encrypted by other users. The assignment of DRA rights to an approved individual provides an IT department with a way to unlock encrypted data in case of an emergency. Data Recovery Agents can be defined at the domain, site, organizational unit, or local machine level. In a small to mid-sized business, the network administrator is often the designated DRA.

In very simple terms, the network administrator uses Microsoft Windows Group Policy in Active Directory to assign everyone a public key for encryption and their own personal private key for decryption. This ensures that users can only decrypt the content they have created. The data recovery agent, however, is assigned a private key capable of unlocking all content encrypted with the public key.

The administrator must generate a Data Recovery Agent certificate which grants the user permission to access the encrypted resources. However, if the DRA certificate is created after the encryption of the resource, the resource cannot be decrypted by the DRA certificate. If you don't already have an EFS DRA certificate, you'll need to create and extract one from your system before you can use Windows Information Protection (WIP).

In this task, you're going to run a command prompt in which you enter the cipher command with a /R parameter. By default, /R creates a 2048 bit RSA recovery key and a DRA certificate; the recovery key is then written to a .PFX file, and the DRA certificate is written to a .CER file. An administrator can then add the contents of the .CER file to the EFS recovery policy to create the recovery key for users and import the .PFX file to recover individual files. The files will be stored in the C:\Users\Admin folder.

The purpose of this task is to create this RSA recovery key so that if the device on which they reside becomes compromised, you can recover the files with this DRA certificate from Intune.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In the Search field on the taskbar at the bottom of the screen, enter **cmd,** and in the menu that appears, select **Command Prompt**.

3. In the **Command Prompt** window, you are going to enter a **cipher** command, which displays or alters the encryption of file directories on NTFS partitions. The **/R** parameter generate an EFS recovery key and a DRA certificate and then stores them in two respective files (for the purpose of this lab, you're going to name each file **DRAcert**; in the real-world, you can name them whatever you wish). The EFS recovery key will be written to a **DRAcert.PFX** file, and the certificate to a **DRAcert.CER** file. <br/>

    At the command prompt, enter the following command and press Enter: <br/>
  
   **cipher /R:DRAcert**

4. You will be prompted to type in a password to protect your .PFX file. Enter **Pa55w.rd** and press Enter.<br/>

    **Note:** The cursor will NOT move when you type in the password, so you will not see what you're typing. You should also write down the password for future use; you will need this in a later task when you try to recover an encrypted file.

5. You will be prompted to type in the password again to confirm it. Press Enter when done. <br/>

    **Note:** If the password and confirmation password did not match, you must repeat the prior two steps.

6. If the password and confirmation password match, you will receive messages indicating that your .CER and .PFX files were created successfully.

7. Close the Command Prompt window.

8. Leave all browser tabs open for the next task.


### Task 4: Create an App Protection Policy

In your role as Holly Dickson, Adatum's Enterprise Administrator, you are now going to create an app protection policy that will protect selected applications from intrusion. In other words, the apps will be protected so that they can only be accessed by individuals who are authorized to do so, such as Adatum employees and other users from your Microsoft 365 tenant. This enables you to use Windows Information Protection (WIP) policies with Windows 10 apps to protect apps without device enrollment.

In this task, you will create a WIP policy that protects an entire collection of recommended apps, as well as an app from the Microsoft Store, which in this case is **Microsoft Power BI**. Since this app produces reports and queries of company trends that may be confidential, Adatum wants to restrict access to it to selected individuals.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your Edge browser, you should have a tab open in the **Microsoft Endpoint Manager admin center** that is displaying the **Compliance1** data compliance policy that you created in the earlier task. <br/>

    In the left-hand navigation pane, select **Apps**.
    
3. In the **Apps | Overview** window, in the left-hand pane under the **Policy** group, select **App Protection policies**.

4. In the **Apps | App protection policies** window, in the menu bar that appears above the list of policies, select **+Create policy.** In the drop-down menu that appears, select **Windows 10**.

5. On the **Create policy** window, note the six steps that appear at the top of the page. You are currently in the step **1 - Basics** page. Enter the following information:

    - Name: **Win10Policy**
    - Description: **Windows Information Protection policy for Windows 10 computers**
    - Enrollment state. **Without Enrollment**

6. Select **Next**.

7. On the step **2 - Targeted apps** page, under the **Protected apps** group, select **+Add**. 

8. In the **Add apps** pane that appears on the right, select the drop-down arrow in the field that currently displays **Recommended apps**. The drop-down menu that appears displays the available app options that you can add to this policy - **Recommended apps, Store apps**, and **Desktop apps**. Since you're first going to add all the recommended apps, select **Recommended apps**. <br/>

    The quickest way to add all the recommended apps is to select the check box to the left of the **Name** column heading; this will select the check boxes for all the apps in the list. Select the **OK** button at the bottom of the window.

9. This returns you to the step **2 - Targeted apps** page. Scroll down past all the recommended apps that you just added and then select **+Add** again.

10. In the **Add apps** pane, you're going to add **Microsoft Power BI**, which is an app from the Microsoft Store. Select the drop-down arrow in the field that currently displays **Recommended apps**, and in the menu that appears, select **Store apps**.

11. In the **Add apps** window, enter the following information and then select **OK**:

    - Name: **Microsoft Power BI**
    - Publisher: **CN=Microsoft Corporation, o=Microsoft Corporation, L=Redmond, S=Washington, C=US**
    - Product Name: **Microsoft.microsoftpowerBIforWindows**

12. Select **OK** to close the **Add apps** pane, and then select **Next**.

13. On the step **3 - Required settings** page, in the **Windows Information Protection mode** setting, select **Block**, and then select **Next**. <br/>

    **Note:** By choosing the **Block** setting, WIP will look for inappropriate data sharing practices and stop the user from completing the action. Blocked actions can include sharing information across non-corporate-protected apps and sharing corporate data between other people and devices outside the organization. Holly has decided to select this option given her concern over the Microsoft Power BI app, which can produce reports and queries of company trends that may be confidential.

14. On the step **4 - Advanced settings** page, scroll down to the **Data protection** section. You will upload the DRA certificate that you created in the prior task, which will allow recovery of encrypted data. <br/>

    To the right of the **Select a file** field, select the **file** icon. In the **File Explorer** window that appears, expand **Local Disk (C:)**, expand **Users**, and then select the **Admin** folder. Scroll down through the files in the **Admin** folder, select **DRAcert.CER**, and then select **Open**.<br/>

    **Note:** DRAcert.CER should now appear in the certificate field in the **Data protection** section. The DRAcert certificate has now been uploaded to the App Protection policy titled **Win10Policy**. This certificate is now available for use in unencrypting protected files. <br/>

    **Important:** At this point in a real-world scenario, to maintain device integrity, you should copy your data recovery certificate to an offline location on a thumb drive or stored in a program for keys and passwords. You should also create a backup of this file and store it at another location. The certification is how you recover files using Intune. If the certificate is not saved, then you cannot recover the file using Windows Information Protection if the device ever becomes compromised. For this lab, you will not store the certificate to an offline device.

15. Select **Next**.

16. On the step **5 - Assignments** page, under **Included groups**, select **Add groups**. Holly wants to limit this policy to the members of the **WIP Users** group, which is the group of users selected to participate in compliance testing for Adatum's pilot project. <br/>

    In the **Select groups to include** pane, select **WIP users**, and then select the **Select** button at the bottom of the pane.

17. Select **Next**.

18. On the step **6 - Review + create** page, review the policy settings. If anything needs to be fixed, select **Previous** and make the necessary corrections. However, if everything looks correct, select **Create**.

19. On the **Apps | App protection policies** window, **Win10Policy** should appear in the list of policies. However, note that its **Deployed** status is **No**. It only takes a few seconds for the policy to be deployed, so select **Refresh** on the menu bar and the **Deployed** status should change to **Yes**.

20. Leave all browser tabs open for the next task.

You have just created a new App Protection Policy (APP), which is also referred to as a Windows Information Protection (WIP) policy.


### Task 5: Create a packaged App rule for the store apps

Packaged apps, also known as Universal Windows apps, are based on an app model that ensures that all the files within an app package share the same identity. Therefore, it is possible to control the entire app using a single AppLocker rule as opposed to the non-packaged apps where each file within the app could have a unique identity. An AppLocker rule for a packaged app controls both the installation as well as the running of the app.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In the Search field on the taskbar at the bottom of the screen, enter **SecPol** and in the menu that appears, select **Local Security Policy**.

3. In the **Local Security Policy** window, in the left-hand pane, expand **Application Control Policies**, expand **Applocker**, and then select **Packaged app Rules**. In the menu bar at the top of the window, select **Action** and then in the drop-down menu that appears, select **Create New Rule.**

4. This starts the **Create Packaged app Rules** wizard. On the **Before You Begin** page, select **Next.**

5. On the **Permissions** page, make sure the **Action** option is set to **Allow** and the **User or group** is set to **Everyone**, and then select **Next**.

6. On the **Publisher** page, under the **Use an installed packaged app as a reference** option, select the **Select...** button.<br/>

    **Note:** It may take around 30 seconds for the **Select applications** window to appear.

7. In the **Select applications** window, pick the app that you want to use as the reference for your rule. For this lab, enter **one** in the **Search** field, and then in the list of results, select the check box to the left of **OneNote**. Select **OK**.

8. On the **Publisher** page, select the **Create** button at the bottom of the page.

9. If a dialog box appears asking whether you want to create default rules, select **No**. You must not create default rules for your WIP policy.

10. In the **Local Security Policy** window, in the left-hand pane, right-click on **AppLocker** and select **Export policy.**

11. In the **Export policy** File Explorer window, you will export and save your new policy as an XML file. Select the **Documents** folder, enter **apprule1** in the **File name** field, verify the **Save as type** field displays **XML (\*.xml)**, and then select **Save**.

12. An **AppLocker** dialog box appears displaying a message that **1 rules were exported from the policy**. Select **OK.**

13. In the **Local Security Policy** window, under **AppLocker**, select **Executable Rules**, and then right-click on **Executable Rules**. In the menu that appears, select **Create New Rule.**

14. On the **Before You Begin** page, select **Next.**

15. On the **Permissions** page, make sure the **Action** option is set to **Allow** and the **User or group** is set to **Everyone**, and then select **Next.**

16. On the **Conditions** page, select the **Path** option and then select **Next**.

17. On the **Path** page, select the **Browse Folders....** button (do not confuse this with the **Browse Files** button).

18. In the **Browse For Folder** window, select **Local Disk (C:)**, select **Program Files**, and then select **OK**. Select **Next**.

19. On the **Exceptions** page, you are not adding any exceptions, so select **Next**.

20. On the **Name and Description** page, select the **Name** field, replace the existing content by entering **exerule1**, and then select **Create**.

21. If an **AppLocker** dialog box appears asking if you want to create the default rules, select **No**.

22. In the **Local Security Policy** window, in the left-hand pane, right-click on **AppLocker** and select **Export policy.**

23. In the **Export policy** File Explorer window, you will export and save your new policy as an XML file. Select the **Documents** folder, enter **exerule1** in the **File name** field, verify the **Save as type** field displays **XML (\*.xml)**, and then select **Save**.

24. An **AppLocker** dialog box appears displaying a message that **2 rules were exported from the policy**. Select **OK.**

25. In the **Executable Rules** folder right click on **exerule1**, then select **Delete**.

26. An **Applocker** warning window will appear asking if your are sure that you want to delete the selected rule. Select **Yes**.

27. Under the **Applocker**section, select **Package app Rules**.

28. In the **Package app Rules** window, right click on the **Microsoft.OneConnect** rule, then select **Delete**.

29. An **Applocker** warning window will appear asking if your are sure that you want to delete the selected rule. Select **Yes**.

30. Close the Local Security Policy window.

31. After you've created your XML files, you will import one of them by using **Microsoft Intune**, which you will do in the next task. 


### Task 6: Import a list of protected apps using Endpoint Manager

The purpose of this task is to show you how to use Intune to push an app to a device just like a Group Policy Object (GPO). In this task, you will use Notepad. In a previous task, Notepad was included as one of the recommended apps in the App protection policy that you created. In this task you will import into Intune the App protection policy (**apprule1.xml**) that you exported in the prior task.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, you should have the **Microsoft Endpoint Manager admin center** portal open in a tab titled **Apps - Microsoft Endpoint Manager admin center**. Select this tab.

3. In the **Apps – App protection policies** window, it displays the list of app protection policies. In this list, select **Win10Policy**.

4. In the **Intune App Protection** window, in the middle pane under **Manage**, select **Properties**.

5. In the **Intune App Protection | Properties** window, the detail pane displays the Intune App Protection properties by group (for example, Basics, Targeted apps, Required settings, and so on). Select **Edit** that appears next to the **Targeted apps** group.

6. In the **Edit policy** window, scroll down past the list of Protected apps and then select **+Import**.

7. In the **Import apps** pane that appears, select the folder icon that appears to the right of the **Select a file** field.

8. In the **File Explorer** window that appears, select the **Documents** folder, select the **apprule1.xml** file, select **Open**, and then at the bottom of the **Import apps** pane, select **OK**.<br/>

    **Note:** This imports the file, and the apps are added to your **Protected apps** list.

9. On the **Edit policy** window, select the **Review + save** button that appears at the bottom of the window, and then select **Save**.   

10. You now want to create a file that you're going to encrypt using Windows Information Protection. In the search field on your taskbar, enter **Notepad**, and then in the menu, select **Notepad**.

11. In the **Notepad** window, enter **This is a WIP encryption test** and then select **File**, select **Save as,** select the **Documents** folder, enter **apptest1** as the **File name**, and then select **Save.**

12. Close Notepad.

13. In the search field on your taskbar, enter **cmd**, and then in the menu, right-click on **Command Prompt** and select **Run as administrator**.

14. In the **Command Prompt** window, at the prompt, enter the following command to encrypt the apptest1.txt file (the /e parameter directs the cipher command to encrypt the file):<br/>

    **cipher /e   C:\Users\Admin\Documents\apptest1.txt**

15. Leave the Command Prompt window open for the next task, but minimize it for now.


### Task 7: Recover data using the EFS DRA certificate

The purpose of this task is to show you how to recover a file that has been encrypted using WIP if the Windows 10 device on which it resides has been recovered after having been misplaced or stolen. In this case, you will decrypt the apptest1.txt file that you earlier encrypted. In a real-world scenario, you would start out by copying your WIP-encrypted file to a location where you have admin access; however, in this lab, we're simply going to point to the apptest1.txt file to keep things simple.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. You must now install the **DRAcert.PFX** file. To do so, select the **File Explorer** icon on the taskbar at the bottom of the screen. Maximize the **File Explorer** window.

3. In **File Explorer**, expand **Local Disk (C:)**, expand **Users**, and select **Admin**.

4. In the list of files in the **Admin** folder, double-click on the **DRAcert.PFX** file. This initiates the **Certificate Import Wizard**.

5. On the **Welcome to the Certificate Import Wizard** page, select the **Current User** option and then select **Next**.

6. On the **File to import** page, select **Next.**

7. On the **Private key protection** page, in the **Password** field, enter the password that you assigned to the DRAcert file that you created in Task 2 (in a real-world scenario, you were instructed to write this down for future use). For this lab, enter **Pa55w.rd**, which was the password that you assigned to the DRAcert file. To verify what you typed, select the **Display Password** check box. Select **Next**.

8. On the **Certificate store** page, select **Next.**

9. On the **Completing the Certificate Import Wizard** page, select **Finish.**

10. On the **Import was successful** dialog box, select **OK**.

11. You should still have a **Command Prompt** window open from the previous task. Select the **Command Prompt** icon on the taskbar to display the window. If you closed the Command Prompt window at the end of the prior task, then open a command prompt with elevated rights.

12. In the Command Prompt window, run the following command to decrypt the apptest1.txt file (the /d parameter directs the cipher command to decrypt the file):<br/>

    **cipher /d  C:\Users\Admin\Documents\apptest1.txt** <br/>
    
    A message should be displayed in the Command Prompt window indicating one file was decrypted.

13.	Close the Command Prompt and File Explorer windows.

14. Leave all browser tabs open for the next task.


### Task 8: Configure enrollment restrictions
When enrolling devices to Microsoft Intune, you have the option to Allow or Block personally owned devices from being enrolled. This is done by restricting what device type platforms you want to allow when devices are enrolled. For example, if you configured Intune to only allow iOS devices to be enrolled and a user attempts to enroll an Android device, the operation would be blocked from enrolling.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your Edge browser, you should have a tab open for the **Microsoft Endpoint Manager admin center** that's displaying the **Intune App Protection | Properties** window. In the left-hand navigation pane, select **Devices**. <br/>

3. In the **Devices| Overview** window, the **Device enrollment** section appears in the middle of the page's navigation pane. Under this section, select **Enroll devices.**

4. In the **Enroll devices | Windows enrollment** window, in the navigation pane for this page, select **Enrollment device platform restrictions**.

5. In the **Enroll devices | Enrollment restrictions** window, in the **Device type restrictions** section, on the **Default** restriction type, select **All users**.

6. In the **All Users** window, the **Manage** section appears towards the top of the page's navigation pane. Under this section,  select **Properties.**

7. In the **All Users | Properties** window, select **Edit** that appears next to **Platform settings**.

8. In the **Edit restriction** window, under the **Platform** column, select **Block** for the **iOS/iPadOS** and **macOS** types, select the **Review + save** button at the bottom of the screen, and then review your changes. Both platform settings should display **Block (edited)** under the **Platform** column. All other device types should be allowed. Select **Save.**

9. In the navigation thread at the top of the page (**Home > Devices > Enroll devices > All users**), select **Enroll devices**. 

10. In the **Enroll devices | Enrollment restrictions** window, in the **Device limit restrictions** section, on the **Default** row, select **All users**.

11. In the **All Users** window, in the middle pane under the **Manage** section, select **Properties.**

12. In the **All Users | Properties** window, select **Edit** that appears next to **Device limit**.

13. In the **Edit restriction** window, select the **Device limit** field, in the drop-down menu select **3**, and then select **Review + save.** Review your change and then select **Save.**

14. Leave all browser tabs open for the next task.


### Task 9: Review device configuration profiles

The purpose of this task is to simply review the different platforms that are available to be assigned to a device configuration profile. You will not create a profile; you will simply review the platforms that are available to assign to a profile.

1. You should still be logged into LON-CL1 as the **Admin** and into Microsoft 365 as **Holly Dickson**.

2. In your **Edge** browser, you should have a tab open for the **Microsoft Endpoint Manager admin center** that's displaying the **All Users | Properties** window. In the left-hand navigation pane, select **Devices**.

4. On the **Devices | Overview** window, the **Policy** section appears in the middle of the page's navigation pane. Under this section, select **Configuration profiles**.

5. On the **Devices |Configuration profiles** page, select **+Create profile** that appears on the menu bar above the list of profiles.

6. On the **Create a profile** pane, select the **Platform** field to see the different platforms that are available. **Do not select any option.** The purpose of this task is to simply see what platforms are available that can be assigned to a new device profile, should you want to ever create one.

7. Close the **Create a profile** pane.

8. Leave all browser tabs open for the next lab exercise.


# Proceed to Lab 9 - Exercise 4
