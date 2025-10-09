# Configuring ODA on PeopleSoft instance 

## Introduction

- This lab will guide you to connect the PeopleSoft environment with the Requisition Skill.

Estimated Time: 60 minutes

### Objectives

- Connect the Requisition Bot to the FSCM PeopleSoft instance.

## **Step 1:** Proxy user creation

1. Login to PeopleSoft with the admin credentials.

2. Go to Navigator and then select PeopleTools > Security > User Profiles.

    ![](images/security.png " ")

3.  Add a new user profile - PSFTPROXY. Click on the Add button.

    ![](images/addpsftproxy.png " ")

4. Select the Symbolic ID as SYSADM1, type your new password and confirm the password.

   ![](images/upgeneral.png " ")

5.  On the next tab, Update the ID type as "None". 

    ![](images/upid.png " ")


6.  Now select the roles as follows and click the Save button.

    ![](images/uproles.png " ")


## **Step 2:** Configure Bot ID

7.  Navigate to Enterprise Components > Chatbot Configurations > Bot Definition page

    ![](images/chatconfig.png " ")

8.  Set the ODA Release Version as – On or After 19.10 and enter the ODA URI which you copied in the *Notepad*.

    ![](images/botdef.png " ")

    Ex: ODA Server URI: oda-XXXX-da2.data.digitalassistant.oci.oraclecloud.com

9. Click Add to open the Add Bot Definition Page. Enter the Bot ID. 
    ![](images/Botid.png " ")

10. Add the Oracle web channel ID which you generated in *Lab 1* in the Bot ID field and select the EOCB Client User role to this bot definition. Now hit the Save button.

    ![](images/maintainbotdef.png " ")

## **Step 3:** Configure Chatbot from a tile

11. Navigation People Tools> Portal> Structure and Content.

12. Click on Add Content Reference. 

    ![](images/addcontentref.png " ")

13. Create new content reference by entering the Name, Label, look up for the Node name and Portal URL as follows:

        <copy>c/EOCB_MENU_FL.EOCB_CLIENT_FL.GBL?BOTID=NEW_SKILL</copy>

    ![](images/contentrefgen.png " ")

    *NOTE: Copy the Node name in a Notepad.*

14. Switch to the Security tab and select the role name as EOCB\_Client\_User from the permission list. 

    ![](images/permissionlist.png " ")

15. Switch to the Fluid Attributes tab and update the following fields:

    Image Name: Click on the search icon and select the image name by looking up for "Chat Client" in the description

    ![](images/fluidatt.png " ")

    Display in: Modal
    
    Modal Parameters: Update the parameter as follows:
    
        <copy>sStyle@frame-pt_chatclientpage;bAutoClose@0</copy>
    

    Folder: In the Tile Repository section look up for "Employee Self Service" in the Portal label and select the fold and click on the Save button.

## **Step 4:** Add Tile to Employee Self Service Home Page

16. Navigate to Homepage > Select Personalize Homepage.

17. Select Add Tile, then search for Employee Self Service, choose New_Skill and save it.

    ![](images/addtile.png " ")

## **Step 5:** Add ePro Requester Inquiry Bot and EOCB Client User permissions to the Admin user 

18. Go to Navigator > PeopleTools > Security> User Profiles > User Profiles and then look up for the user "VP1"

19. Switch to the Roles tab and click on the + button next to any user role. Now, look up "ePro Requester Inquiry Bot" and add the role.

    ![](images/epro.png " ")

20. Also, add "EOCB Client User" role and click on the Save button.

    ![](images/EOCB.png " ")  

## **Step 6:** Verify Restricted Services

20. Go to Navigator > PeopleTools > Integration Broker > Configuration > Service Configuration > Restricted Services and search with the keyword "PTCB".

21. Uncheck the Restricted service so that you can edit Service configurations. Now save all the changes.

    ![](images/restricted.png " ")

22. Now, go to Navigator > PeopleTools > Integration Broker > Integration setup > Service Operations and search for the service "PTCB\_APPL\_SVC".

23. Update the req. verification field as "Basic Authentication" instead of "SSL" for both Service Operations "PTCB\_APPL\_SVC\_GET" and "PTCB\_APPL\_SVC\_POST".
    ![](images/serviceop.png " ")

    ![](images/reqauth.png " ")

Note: The Basic Authentication uses a username and password to make any request whereas SSL Authentication uses securely encrypted certificate based authentication. You can use any of them based on your Organization's need.

## **Step 7:** Update the Authentication type for the Application Service

24. Navigate to PeopleTools > Integration Broker > Web Services > Application Services >  Application Services.

25. Search for PT_CONFIGIRATION and click on the Configure button. 

26. By default, the authentication type is OAuth but switch that to PS ODA Authentication and save the changes.

    ![](images/ptconfig.png " ")

## **Step 8:** Update the Skill Configuration

27. Switch back to the ODA console and navigate to the Skill Setting > Configuration tab. Set the following values for:

    PSFSCMbaseurl: It denotes the base url of the application service. Replace with an actual server, port and nodename.
            
            <copy>https://<WebserverName.com>:<port>/PSIGW/RESTListeningConnector/<nodeName>/PTCB_APPL_SVC.v1</copy>

    Note: Webserver name - Public IP address of the PeopleSoft Instance and Nodename - Paste the Nodename which you copied in *Step 2*.

    PSFSCMuserid: Set the PeopleSoft proxy user who has access to invoke application services. To start with, Let us leave it, as it is (PSFTPROXY).

    PSFSCMpassword: It denotes the password for a Proxy user which you set in *Step 1*. 

    ![](images/config.png " ")

    

## Acknowledgements
 - **Author** -  Saipriya Thirvakadu | Cloud Engineer 
 - **Contributors** - Max Grossman | Cloud Engineer, Mukul Bihari Prasad | Principal Solutions Architect
 - **Last Updated By/Date** - Saipriya Thirvakadu, Cloud Engineer, January 2021

