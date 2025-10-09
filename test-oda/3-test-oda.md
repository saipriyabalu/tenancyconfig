# Test the Requisition Skill

## Introduction

- This lab will guide you to test the Requisition Skill on the PeopleSoft instance.

Estimated Time: 5 minutes

### Objectives

- Test the Requisition Skill deployed on FSCM PeopleSoft instance

## **Step 1:** Check the Requisition details

1. On your PeopleSoft instance, navigate to the Employee Self Service Page.

    ![](images/EmployeeSelfService.png " ")

2. Select the eProcurement tile > My Requisitions. If you don't find any requisitions, go back to the eProcurement page and create a Requisition.

3. Now select '>' next to any Requisition name to check the details of the requisition.

    ![](images/myreq.png " ")

4. Copy the Item ID in a *Notepad* to verify the item details from the bot.

    ![](images/reqdetails.png " ")

## **Step 2:** Test your Skill

1. Go back to the Employee Self Service page and select the New_Skill tile to access your bot.

    ![](images/new_skill.png " ")

2. Test your bot.

    - User: Hi
    - Bot: Hello! I am a virtual assistant. I can help you inquire on the status of your Requisitions. 
    You can ask me questions like: 

        1) Where is Item (Item ID)?  
        2) Where is my ''Item Description'' (part or full Item description)?

    - User: where is item XXX?
    - Bot: Requisition(s) for Item XXX ......

      ![](images/bot1.png " ")

      ![](images/bot2.png " ")  

## **Summary**

Congratulations, You have successfully deployed the Requisition Skill on PeopleSoft instance.

## Acknowledgements
 - **Author** -  Saipriya Thirvakadu | Cloud Engineer 
 - **Contributors** - Max Grossman | Cloud Engineer, Mukul Bihari Prasad | Principal Solutions Architect
 - **Last Updated By/Date** - Saipriya Thirvakadu, Cloud Engineer, January 2021
