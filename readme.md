# MS-101T00: Microsoft 365 Mobility and Security

- **[Download Latest Student Handbook and AllFiles Content](../../releases/latest)**
- **Are you a MCT?** - Have a look at our [GitHub User Guide for MCTs](https://microsoftlearning.github.io/MCT-User-Guide/)
- **Need to manually build the lab instructions?** - Instructions are available in the [MicrosoftLearning/Docker-Build](https://github.com/MicrosoftLearning/Docker-Build) repository

## What are we doing?

- To support this course, we will need to make frequent updates to the course content to keep it current with the Azure services used in the course.  We are publishing the lab instructions and lab files on GitHub to allow for open contributions between the course authors and MCTs to keep the content current with changes in the Azure platform.

- We hope that this brings a sense of collaboration to the labs like we've never had before - when Azure changes and you find it first during a live delivery, go ahead and make an enhancement right in the lab source.  Help your fellow MCTs.

## How should I use these files relative to the released MOC files?

- The instructor handbook and PowerPoints are still going to be your primary source for teaching the course content.

- These files on GitHub are designed to be used in conjunction with the student handbook, but are in GitHub as a central repository so MCTs and course authors can have a shared source for the latest lab files.

- It will be recommended that for every delivery, trainers check GitHub for any changes that may have been made to support the latest Azure services, and get the latest files for their delivery.

## What about changes to the student handbook?

- We will review the student handbook on a quarterly basis and update through the normal MOC release channels as needed.

## How do I contribute?

- Any MCT can submit a pull request to the code or content in the GitHub repro, Microsoft and the course author will triage and include content and lab code changes as needed.

- You can submit bugs, changes, improvement and ideas.  Find a new Azure feature before we have?  Submit a new demo!

## Notes

It was brought to are attention that a change was made during the provisioning of the Microsoft 365 tenants. Some features may not enable from the tenant UI when the student selects a button to enable a feature. This issue is being addressed with great haste. However, if the issue isn't resolved by August 9, 2021. Please have your students run the following commands before you start your lecture. 

1. Type **Powershell** into the **search bar** located on the taskbar. 
2. Right click on the powershell app and **Run as Administrator**.
3. when the Powershell app opens enter the following commands. 
       
       Set-ExcutionPolicy RemoteSigned
       
4. Type the letter **A** and press enter to agree to all 
       
       Install-Module -Name ExchangeOnlineManagement
       
5. Type the letter **A** and press enter to agree to all 
       
       Connect-ExchangeOnline
       
6. a Sign page will open, Enter in the **Microsoft 365 global administrator account** and **Password**.
       
       Enable-OrganizationCustomization
 
 You may need to have your students run the previous command multiple times (up to 3) in order for the Commandlet to fully provision.


### Classroom Materials

It is strongly recommended that MCTs and Partners access these materials and in turn, provide them separately to students.  Pointing students directly to GitHub to access Lab steps as part of an ongoing class will require them to access yet another UI as part of the course, contributing to a confusing experience for the student. An explanation to the student regarding why they are receiving separate Lab instructions can highlight the nature of an always-changing cloud-based interface and platform. Microsoft Learning support for accessing files on GitHub and support for navigation of the GitHub site is limited to MCTs teaching this course only.
