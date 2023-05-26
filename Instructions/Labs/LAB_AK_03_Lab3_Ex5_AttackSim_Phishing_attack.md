# Learning Path 3 - Lab 3 - Exercise 5 - Conduct a Spear Phishing attack using Attack Simulation training

Holly Dickson is concerned that some users at Adatum may require education about phishing attacks. As part of her pilot project, Holly has decided to use the Microsoft 365 Attack simulation training feature to determine her users' susceptibility to phishing attacks.


### Task 1: Enable Multifactor Authentication for the Global Admin
To use Microsoft's Attack simulation training feature to simulate a phishing attack, you must first enable Multifactor Authentication (MFA) for either your entire organization or for just the Global admin who will run the simulation. For her pilot project, Holly does not want to set up MFA for all the Adatum users at this point in time; therefore, she will enable MFA for her user account only, and then after she finishes running the Attack simulation training, she will turn MFA back off. 

**Important:** To implement MFA, you will need to use your mobile phone to receive a verification code so that you can enter it into your tenant as a second form of authentication. If you do not have a phone, you will have to skip this lab. If this is the case, notify your instructor, who can potentially partner you with another student to follow along through this lab.

1. Switch to the **LON-CL1** VM, where you should still be logged in as the local **Admin** account. If necessary, log in as the **Admin** with a password of **Pa55w.rd**. 

2. In your **Edge** browser, you should still be logged into Microsoft 365 as **Holly Dickson**. To enable MFA for Holly Dickson's user account, select the **Microsoft 365 admin center** tab in your browser, and then in the left hand-navigation pane, select **Users** and then select **Active users**.

3. In the **Active users** window, on the menu bar at the top of the user list, select **Multi-factor authentication**. If this option does not appear on the menu bar, select the **ellipsis (More actions)** icon, and in the drop-down menu that appears, select **Multi-factor authentication**.

4. A **Configure multi-factor authentication (MFA)** window appears in a new Edge browser tab. Select the **Get started** button.

5. On the **Enforce multifactor authentication** window, select **Next**.

6. On the **Configure Adaptive MFA using Conditional Access** page, at the end of the opening paragraph, select **Check status here**.

7. On the **multi-factor authentication** page, the **users** tab is displayed by default. Note the MFA status for all existing user accounts is **Disabled**. Select the check box for **Holly Dickson**, and in Holly's properties pane that appears on the right, under the **quick steps** section, select **Enable**.

8. On the **About enabling multi-factor auth** dialog box that appears, select the **enable multi-factor auth** button. 

9. When the **Updates successful** dialog box appears, select **close**. In the **multi-factor authentication** window, verify Holly's MFA Status has changed to **Enabled**. 

10. You must now sign out of Microsoft 365 as Holly and then sign back in using MFA. The first time you sign back in after having MFA enabled for your user account, you will be asked for the authentication information needed for MFA, such as your phone number and authentication options. You will then be texted a verification code to validate the authentication process works. You will perform these steps in the remaining portion of this task.<br/>

	You must begin by signing out of Microsoft 365 as Holly, so select the **HD** user icon in the upper right corner of the browser and in the **Holly Dickson** window that appears, select **Sign out**. 

11. Once you are signed out, close all the browser tabs. This will close your Edge browser.

12. Select the **Edge** icon on your taskbar to open a new browser session. In your browser go to the **Microsoft Office Home** page by entering the following URL in the address bar: **https://portal.office.com/** 

13. In the **Pick an account** window, select **Holly@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix provided by your lab hosting provider) and then select **Next**. In the **Enter password** window, enter **User.pw1** and select **Sign in**.

14. Because MFA is enabled for Holly, a **More information required** window appears. Select **Next**.

15. On the **Microsoft Authenticator** page, you can download this mobile app or use a different method for MFA verification. For the purposes of this lab, we recommend you use your mobile phone so that you do not have to take time installing the Microsoft Authenticator app that you may not use again after this training class. Select the **I want to set up a different method** option at the bottom of the window. 

16. On the **Choose a different method** dialog box that appears, select the drop-down arrow in the **Which method would you like to use?** field, select **Phone**, and then select **Confirm**. 

17. In the **Phone** window that appears, under **What phone number would you like to use?** field, select your country or region, and then in the field next to it, enter your phone number (in the format **nnn-nnn-nnnn**). Verify the **Text me a code** option is selected and then select **Next**.

18. Retrieve the verification code from the text message that is sent to your phone.

19. In the **Phone** window, enter the 6-digit verification code in the code field and then select **Next**. When the **Phone** window displays a message indicating your phone was registered successfully, select **Next**.

20. On the **Success!** page, select **Done**.

21. If a **Stay signed in?** dialog box appears, select the **Don’t show this again** check box and then select **Yes.** 

22. On the **Microsoft Office Home** tab, select the **Admin** icon that appears in the column of app icons on the left-side of the screen. This opens the **Microsoft 365 admin center** in a new browser tab. This will prepare you for the next lab exercise when you disable MFA for Holly Dickson after completing the Attack simulation training.

23. In the **Microsoft 365 admin center**, select **Show all** in the navigation pane. Under **Admin centers**, select **Security**. This will open the **Microsoft 365 Defender** portal. You will resume from here in the next task when you launch a spear phishing attack using Attack simulation training.  

24. You have now configured MFA for Holly Dickson, you have signed into the **Office 365** portal as Holly using MFA, you have opened the Microsoft 365 admin center for future labs, and you are ready to run the Attack simulator training in the Microsoft 365 Defender portal. Leave everything as is in your VM and proceed to the next task.


### Task 2: Configure and launch a Spear Phishing attack

Now that Holly has turned on MFA, she is ready to run Microsoft 365's Attack simulation training feature and launch a simulated spear phishing attack. This will provide visibility into how well Adatum is prepared to handle this type of security attack. 

Microsoft 365 includes an Attack simulation training feature that enables you to create simulations and run them against all your users or a select group of users. Each phishing attack includes what is referred to as the "payload", which is the message in the email that contains the malicious component hackers use to gather information, deposit malicious code, and so on. The Attack simulation training feature includes a number of payload templates that you can choose from, and you can create your own payload if you so desire. 

In this lab exercise, you will use one of the existing payload templates. In the next lab exercise, you will create your own custom payload.

1. You should still be on **LON-CL1**, and you should still be logged in as the local **Admin** account. If necessary, log in as the **Admin** with a password of **Pa55w.rd**.

2. You should still have the **Microsoft 365 Defender** portal open in your **Edge** browser from the prior task. If not, enter **https://security.microsoft.com** in the address bar, and then if you receive the dialog box asking for a second form of authentication, proceed through the verification process. If not, sign-in using Holly's user id and password.

3. In the **Microsoft 365 Defender** portal, under **Email & collaboration** in the left-hand navigation pane, select **Attack simulation training**. If a **Welcome to Attack simulation training** window appears, select **Close**.

4. On the **Attack Simulation training** page, Holly has decided to conduct an simulated account breach in which she will use a URL to try and obtain usernames and passwords. This is referred to in the Attack Simulator as a **Credentials Harvest** attack. <br/>

	There are multiple ways to run a simulation, as you can see on the **Overview** tab that's displayed by default. For the purpose of this lab, select the **Simulations** tab, and then select **+Launch a simulation**. This initiates the **Create Simulation** wizard.

5. On the **Select Technique** page, the **Credential Harvest** technbique is selected by default. Select the **View details of Credential Harvest** link for this option. On the **Credential Harvest** pane that appears, review the the **Description** and the **Simulation steps** for this type of attack. When you're done, close the **Credential Harvest** pane.

6. On the **Select Technique** page, verify the **Credentials Harvest** option is selected, and then select **Next**.

7. In the **Simulation** wizard, the steps involved in the simulation are displayed in the left-hand pane. While you can manually create a phishing campaign, it is recommended that you take advantage of the available templates that will prefill most of the information for you. The key to a successful phishing attack is to create a very intriguing, real-world looking email, and the templates provide very creative solutions. <br/>

	On the **Name Simulation** page, provide the following information: 
	- Simulation Name: **PhishingTest1**
	- Description: **This simulation provides insight on targeted email threats against users inside the company**

8. Select **Next**.

9. On the **Select payload and login page** window, select the check box to the left of the **2 Failed Messages** payload. Select **Next**. 

10. On the **Target Users** page, select the **Include all users in my organization** option. This will display all of Adatum's users. Select **Next**.

11. On the **Exclude users** page, you won't be excluding any users, so select **Next**

12. On the **Assign Training** page, under the **Preferences** section, the **Assign training for me (Recommended)** option should be selected by default (if not, select it now). Select the **Due Date** field. In the drop-down menu that appears, select **7 days after Simulation ends** and then select **Next**.

13. On the **Select Phish landing page** window: <br/>

	- Verify the **Use landing pages from library** option is selected (if not, then select it now).
	- At this time, do NOT select the checkbox below **Payload indicators** to add payload indicators to email. You will select this option in a later step.
	- Select the appropriate language in the **Select default language** field.
	- Under the **Global landing pages** tab, double-click **Microsoft Landing Page Template 1**. A preview of the **Microsoft Landing Page Template 1** appears. This preview panel provides an example of what the landing page will look like when someone experiences a phishing attack and the simulation uses **Microsoft Landing Page Template 1**. Scroll down through this preview panel and review the features. When you're finished, select the **Close** button at the bottom of the preview panel. 
	- On the **Select Phish landing page** window, select the checkbox below **Payload indicators** to add payload indicators to email.
	- Double-click on **Microsoft Landing Page Template 1** once again. In the preview pane that appears, this time note the payload indicators that are highlighted.
	- Close the preview pane.
	- On the **Select Phish landing page** window, select the checkbox below **Payload indicators** to clear it.

14. You will now look at some of the other landing page templates until you find one that you want to use for this simulation. On the **Select Phish landing page** window, double-click one of the other templates to open its preview pane. Examine the preview pane and note how the landing page for this template is different from **Microsoft Landing Page Template 1**. When you're finished, select the **Close** button at the bottom of the preview pane.

15. Repeat the prior step as many times as you would like until you find a template that you want to use for this simulation. Once you're satisfied with a template, verify the checkbox is selected for that template and then select **Next**.

16. On the **Select end user notification** page, choose how you want the end user to be notified. For the purpose of this lab, select **Microsoft default notification (recommended)**. In the list of notifications that appears, configure the following notifications:

	 - Microsoft default positive reinforcement notification - set **Delivery preferences** to **Deliver after simulation ends**
	 - Microsoft default training reminder notification - set **Delivery preferences** to  **Weekly**

17. Select **Next**.

18. On the **Launch Details** page, select the **Launch this simulation as soon as I'm done** option and then select **Next**.

19. On the **Review Simulation** page, review the entered information. If anything needs to be changed, select the appropriate **Edit** option to make the change. Once everything is correct, select **Submit**. It may take a few minutes for the system to submit the simulation request.

20. On the **Simulation has been scheduled for launch** page that appears, select **Done**.

21. On the **Attack simulation training** page, note the **PhishingTest1** simulation appears. If it doesn't appear, select **Refresh** on the menu bar above the list of simulations.

22. Leave your browser open in LON-CL1 and do not close any of the tabs.


### Task 3: Review the attack simulation results

In this task, you will verify whether Adatum has received the email that you configured in the Attack simulation training. You will then review the diagnostic feedback associated with the Spear Phishing attack that you simulated.

1. Switch to the **LON-CL2** VM and, if necessary, log in as the local **Admin** account with a password of **Pa55w.rd**.

2. In the Edge browser, you should still be logged into Outlook as the **MOD Administrator** from the prior lab. To log out of Outlook as the MOD Administrator, select the **MA** initials in the upper right hand corner of the screen. In the **MOD Administrator** window that appears, select **Sign out**.

3. Close all browser tabs except for the **Sign out** tab. In the **Sign out** tab, enter the following URL in the address bar to navigate directly to Outlook on the web: **https://outlook.office365.com**.
 
4. In the **Pick an account** window, select **Use another account**. 

5. In the **Sign in** window, enter **LynneR@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix ID provided by your lab hosting provider), and then in the **Enter password** window, enter **User.pw1** and select **Sign in**. 

6. In Lynne's Outlook Inbox, you should see the spear phishing email that was sent by the Attack Simulator. The subject of the message should be **2 Failed messages to you**. Select the email to open it and review the details in the body of the message. 

	**NOTE!** It can take up to 15 minutes for the email to arrive.  Wait for the email before proceeding.

7. Select the **View Returned Messages** button in the email. Even though you know this is a spear phishing attack, this will enable you to see the effect of doing so in the Attack Simulator report that tracks the results of the spear phishing campaign.

8. In the **Sign in** dialog box that appears, enter **LynneR@xxxxxZZZZZZ.onmicrosoft.com** (where xxxxxZZZZZZ is the tenant prefix ID provided by your lab hosting provider), and then enter **User.pw1** in the **Enter password** window. Select **Sign in**. 

9. This displays a web page that explains how you have been redirected to it as part of a Phishing awareness test being run by your organization. Read through the contents of this site, which uses the landing page template that you selected in the prior task when setting up the attack simulation.

10. Switch back to **LON-CL1**.

11. In your browser session where you are logged in as Holly Dickson, you should still be on the **Attack simulation training** page. In the list of simulations, double-click the **PhishingTest1** simulation to view the diagnostic results that were captured for this simulation.

12. A **PhishingTest1** page should appear. Review all the information collected for this simulated attack. When you're finished, select the **X** in the upper right-hand corner of the window to close it. 

13. Leave your browser open in LON-CL1 and do not close any of the tabs.
    

# Proceed to Lab 3 - Exercise 6
