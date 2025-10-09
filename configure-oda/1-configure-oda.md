# Configure the Requisition Skill on Oracle Digital Assistant

## **Introduction**

- This lab will guide you through the steps to configure the Requisition Skill on Oracle Digital Assistant.

Estimated Time: 10 minutes

### **Objectives**

- Install and configure the Requisition Skill in Oracle Digital Assistant

## **Step 1:** Install and Configure the Skill

1. Sign in to your ODA instance. Click on the hamburger icon on the left and navigate to Development > Store. 

2. Lookup for "PeopleSoft Epro Requester Inquiry Bot". Now, click on the hamburger icon and select Pull.

    ![](images/pullskill.png " ")

3. You can either use the same bot or select extend if you would like to further customize the Requisition Skill. 

    Update the Display Name and Select the Extend button.

    ![](images/customizeskill.png " ")


## **Step 2:** Create the web channel for this Skill

1. Click on the hamburger icon and navigate to Development > Channels and click on the + Channel button.

2. Enter the Channel name, Description, Channel type - Oracle Web, Allowed Domain - *, Client authentication enabled - uncheck and select Create.

3. Route the channel to the Skill you have configured in Step 1.

    ![](images/webchannel.png " ")

*NOTE: Copy the generated Channel ID and ODA URI - Ex: "oda-XXXX-da2.data.digitalassistant.oci.oraclecloud.com" in a Notepad.*

You may now *proceed to the next lab*.


## Acknowledgements
 - **Author** -  Saipriya Thirvakadu | Cloud Engineer 
 - **Contributors** - Max Grossman | Cloud Engineer, Mukul Bihari Prasad | Principal Solutions Architect
 - **Last Updated By/Date** - Saipriya Thirvakadu, Cloud Engineer, January 2021