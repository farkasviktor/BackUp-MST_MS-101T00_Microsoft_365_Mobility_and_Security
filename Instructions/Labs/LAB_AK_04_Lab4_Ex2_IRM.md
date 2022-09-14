# Learning Path 4 - Lab 4 - Exercise 2 - Validate Information Rights Management 

In this exercise, you will learn how to validate Information Rights Management for both Exchange Online and SharePoint Online.
 
### Task 1 - Validate Information Rights Management for Exchange Online

In the prior exercise, you set up Information Rights Management in Exchange Online for Adatum. In this exercise, you will validate that configuration by sending a protected email from Holly Dickson to Alex Wilber. You will then log into Alex’s mailbox on the Client 2 VM (LON-CL2), open the email, and verify that it’s protected.  

1. On the Client 1 VM (LON-CL1), you should still be logged into the Microsoft 365 admin center as Holly Dickson. 

2. In the earlier exercise in which you created an eDiscovery alert, you opened **Outlook on the web** for Holly. This tab should still be open in your browser, so select it now; however, if you closed Outlook, then open a new tab in your browser and enter the following URL: **https://outlook.office365.com**

3. At the top of the left-hand navigation pane, select **+New message** to create a new email.

4. You want to send the email to **Alex Wilber**. Type **Alex** in the **To** field and select **Alex Wilber** from the list of users that are displayed.

5. Enter **IRM test** in the **Subject** line and then enter some text in the message body. 

6. In the menu bar above the message pane, select **Encrypt** (this option appears because you set up IRM in Exchange in the prior task).

7. This displays a message below it that indicates the message is encrypted. In this message box, select **Change permissions**, which opens a **Change permissions** dialog box.

8. In the **Change permissions** dialog box, in the **Choose how recipients can interact with this message** field, select the drop-down arrow, select **Do not forward**, and then select **OK**. 

**Note**If **Change permissions** option is not available then click on the horizontal ellipsis on the top menu of the new message, select **Encrypt** and then select **Do Not Forward**

9. Select **Send** to send the email to Alex. 

10. Switch to the Client 2 VM (LON-CL2).

11. If you need to log in as the **Admin** account, then do so with a password of **Pa55w.rd**.

12. In an earlier lab exercise, you opened **Outlook on the Web** on LON-CL2 for Lynne Robbins. You must log out as Lynne so that you can sign back in as Alex. <br/>

	Select Lynne's user icon in the upper right corner, and in her **My account** window, select **Sign out**. Once you are signed out, close all tabs in your browser except for the **Sign out** tab. 

13. In your **Edge** browser, in the **Sign out** tab, enter the following URL in the address bar: **https://outlook.office365.com**. 

14. In the **Pick an Account** window, only Lynne's account and the MOD Administrator's account appear. Select **Use another account** and log in as **AlexW@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) with a password of **Pa55w.rd**.<br/>

15. Close the **Welcome** window that appears.

16. In Alex's **Inbox**, verify that he received the email that you sent from Holly that is IRM protected. IRM protected emails display a lock icon to the right of the message. Select the message to display it in the right-hand pane.

17. You should see a message at the top of the message pane that says **This message is encrypted and recipients can’t forward it.** A lock icon should appear next to this message as well, which indicates the message is encrypted. 

18. In the message pane for this email, note how the **Forward** arrow is disabled. Similarly, at the bottom of the email, note how the **Reply** option is enabled, but the **Forward** option is not. 

19. In the message pane for this email, select the **ellipsis (More actions)** icon that appears to the right of the disabled Forward arrow. In the drop-down list that appears, note how the **Print** option is disabled. Encrypted emails can neither be forwarded or printed.

20. You want to remain logged into the Microsoft 365 as Alex Wilber on LON-CL2 for the next task, so leave your browser tabs open and proceed to the next task. 

 
### Task 2 - Validate Information Rights Management for SharePoint Online

In Lab 1, you enabled Information Rights Management for Adatum in SharePoint Online. Ideally, you would have enabled IRM for SharePoint Online at the start of this exercise, just as you did when enabling IRM for Exchange Online. However, since it can take an hour or more for IRM to show up in SharePoint Online once it’s enabled, that task was moved to Lab 1 so that by the time you got to this task, IRM would be ready for you in SharePoint.

You will begin by having Holly create a new SharePoint site collection. You will then configure it for Information Rights Management, share it with Alex Wilber, and then have Alex validate IRM for the site. 

1. Switch to the LON-CL1 VM where you should still be logged into the **Microsoft 365 admin center** as **Holly Dickson**.

2. In the **Microsoft 365 admin center**, scroll down through left-hand navigation pane and under **Admin centers**, select **SharePoint**. This will open the SharePoint admin center in a new browser tab.

3. In the **SharePoint admin center**, in the left-hand navigation pane, select **Sites** and then select **Active sites**.

4. In the **Active sites** window, select **+Create** on the menu bar.

5. On the **Create a site** pane that appears, you must choose the type of site you want to create. Select the **Team site** tile. 

6. On the **Get a team site connected to Microsoft 365 Groups** pane, enter the following information:

	- Site name: **Marketing**  
	
	- Group email address - **Marketing** is filled in automatically after entering the Site name; leave as is
	
	- Site address - **Marketing** is filled in automatically after entering the Site name; leave as is

	- Group owner: Enter **Holly**, and then in the list of users that is displayed, select **Holly Dickson**

	- Select a language: select your language
	
7. Select **Advanced settings** and then enter the following information:

	- Privacy settings: **Private - only members can access this site**
	
	- Time zone - select your time zone

8. Select **Next**.

9. On the **What do you want to add?** pane, enter **Alex** in the **Add members** field and then select **Alex Wilber** from the list of users. Select **Finish**.

10. If the new **Marketing** site collection does not appear in the **Site Collections** list after a couple of minutes, select the **Refresh** icon to the left of the address bar. If it still doesn't appear, wait another minute or two and refresh the list again. Continue until the new site collection appears. 

11. You will now open the new SharePoint site that you just created. In your web browser, open a new tab and enter the following URL in the address bar: **https://xxxxxZZZZZZ.sharepoint.com/sites/marketing** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider)

12. On the **Marketing** site, in the left-hand navigation pane, select **Documents.** 

13. In the **Documents** page for the **Marketing** site, at the top right of the title bar, select the **gear (Settings)** icon and then in the **Settings** drop-down menu that appears, select **Library settings**. Note - it may take a minute or two for the gear icon to appear. 

14. On the **Documents > Settings** page, in the **Permissions and Management** column, select **Information Rights Management**. 

15. On the **Settings > Information Rights Management Settings** page, select the **Restrict permissions on this library on download** check box. 

16. In the **Create a permission policy title** field, enter **Marketing Policy**. 

17. In the **Add a permission policy description** field, enter **Marketing policy for downloads**. 

18. Select **SHOW OPTIONS**. 

19. In the **Configure document access rights** section, select the **Allow viewers to write on a copy of the downloaded document** check box and then select **OK**.

20. On the **Documents > Settings** page, select the **Documents** portion of this page title. This returns you to the **Documents** page for the **Marketing** site.

21. On the **Documents** page, select the **gear (Settings)** icon and then in the **Settings** drop-down menu that appears, select **Site permissions**. 

22. In the **Permissions** pane that appears, select **Site members** and note that only the **Marketing Members** have permission to access the Documents site.

23. To share this Documents site with Alex Wilber, in the **Permissions** pane select the **Add Members** button. In the drop-down menu that appears, select **Share site only**.

24. On the **Share site** pane, enter **Alex** in the field, then select **Alex Wilber** from the user list, verify the **Send email** check box is selected (if not, select it now), and then select **Add**.

25. In the **Permissions** pane, select **Site members** and note that **Alex Wilber** is now included along with the **Marketing Members**.

26. Close the **Permissions** pane. 

27. Select the **Start** icon in the bottom left corner of the taskbar, and then in the Program menu, select **Microsoft Word**.

28. When **Microsoft Word** opens, select **Blank document**.  

29. Enter some text in the document, then save the file to the **Desktop** as whatever file name you wish.

30. Close Word.

31. Since Holly has her Outlook mailbox open, she is simply going to email the file that she just created to Alex. Select the **Outlook on the Web** tab in your browser that contains Holly's mailbox that you just used in the prior task when you emailed Alex.

32. Send an email to Alex Wilber and attach the file that you just created and stored on the Desktop. 

33. Now that Holly has created this new SharePoint site and used IRM to restrict permissions on the site, she has asked Alex Wilber to test this site to validate whether IRM is working for SharePoint Online. Alex will perform this test on the Client 2 (LON-CL2) VM.<br/>

	‎Switch to the **LON-CL2** VM, where you should still have **Outlook on the Web** open in your **Microsoft Edge** browser from the prior task. You should still be logged in as **Alex Wilber**.

34. In the **Outlook on the Web** tab, open the email that you just received from Holly that contains the file Holly created earlier. Save the file to the **Documents** folder on your **C** drive.

35. ‎In the browser, open a new tab and enter the following URL in the address bar to navigate directly to the Marketing site: **https://xxxxxZZZZZZ.sharepoint.com/sites/marketing** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider)

36. If a **We've got a new look** window appears, select **NOT NOW**.

37. On the **Marketing** site, select **Documents** on the left-hand pane.  

38. On the **Documents** page, in the menu bar, select **Upload**, and then in the drop-down menu select **Files**. 

39. In the **File Explorer** window, navigate to the **Documents** folder, which is where you saved the file that Holly emailed to Alex a few steps ago. Select the file and then select **Open**.

	This will upload the file to the **Documents** page in the **Marketing** site collection.

40. In the list of Documents, right-click on the file that you just uploaded, select **Open** in the menu that appears, and then select **Open in browser**. 

41. In Word Online, if a **Your privacy option** window appears, then close it. Verify that a warning message appears at the top of the page indicating a **Marketing policy for downloads** applies to the file. 

42. Try to enter some text in the document. Verify that Alex cannot edit the document in Word Online because it’s protected in this site collection. A **Read-only** information line will display at the top of the page indicating the document is read-only. <br/>

	You have just verified that the Marketing site collection is protected by SharePoint Information Rights Management. The document that Alex just uploaded to the SharePoint Online site is flagged as read-only and cannot be updated.

43. Leave your browser open for the next lab; do not close any of the tabs. 


# Proceed to Lab 4 - Exercise 3
