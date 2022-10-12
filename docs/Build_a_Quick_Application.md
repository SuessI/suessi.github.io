# Build a Quick Application  

<p style="font-size:16px; color:red">This tutorial is currently being updated for the DigitalSuite Studio.</p>  

This tutorial is designed for users who are new to the RunMyProcess platform, it will guide you step-by-step through the stages of a simple application development. The application we will produce includes the main steps that are common to most applications on the platform - creating a project, creating a custom list, creating a web interface, designing a process, adding a web connector and integrating with a spreadsheet.    

Building this application will give you a basic understanding of how the RunMyProcess platform works. Once you are comfortable with this project, we suggest that you move on to other [help tools](/Training/) provided.   

Once you've completed this project, we would like you to let us know [whether you found the guide helpful or not.](http://www.surveygizmo.com/s3/627699/Feedback-Create-a-RunMyProcess-App-in-10-minutes)


**What the application does**  

In the final version of the application, a user will be able to select a currency YYY from a list, in a web interface, and submit it.  

![58](/images/Training/10-Minute_Application/58.PNG)  

Clicking on the Submit button will trigger a workflow process that will:

* Get FX rates from the European Central Bank connector for the currency chosen by the user;
* Assign a task to another user that will display the current FX rate and asks for his/her approval;   
* Upon approval, the application will write the FX rate, the name of the user and the date to a Google spreadsheet [(link)](https://docs.google.com/spreadsheet/ccc?key=0AnS14Z5-lKRldFBsTDFWQ05RYmJqS1pBRkdobm9ZeUE&authkey=CNTQxtgN&authkey=CNTQxtgN#gid=0).


**Let's get started**  

1. To start developing a new application, you must begin by creating a new RunMyProcess project. Click on **New Project** in the **Home** section of the platform.<br>  
   ![Account](/images/Training/10-Minute_Application/account.PNG)

2. Add a **Title** and choose a **designer group** from the choice offered to you - choose a group that you are a member of, this will give you the right to design the project. We encourage you to consult the explanation of how to choose the proper organization and lane [available in the user guide](/Developer_Guide/Development_Environment/Toolbox/Organization/Roles_Entities). Click **Create** to create the new project.<br>
   You can now view the project. The project's resources are listed under **Resource explorer**.<br>
   ![ProjectCreationOrga](/images/Training/10-Minute_Application/project%20creation-orga.PNG)  
   ![ResourcesReview](/images/Training/10-Minute_Application/Resources%20-review.PNG)  

3. As the application will make use of email, we need to include a project that provides emailing capability. Click on **Include a project** (1), select **Mail provider** (2) and then click **OK** (3). The **Mail Provider** project is deployed on all accounts and is the RunMyProcess default email provider.<br>   
   ![IncludeProject](/images/Training/10-Minute_Application/include%20project.PNG)  

4. We are now ready to start designing our process. Click on the + **New** button and select **Process**.<br>
   ![NewProcess](/images/Training/10-Minute_Application/new-process.PNG)  

5. In the window that appears, select the group that will have the right to trigger the process. Please note that the developer/designer also needs to be a member of the group in order to trigger the process. After choosing a group add a Process name, and click **Create**. The name given to the process should be the same as the name of the application that we are creating.<br>
   ![ProcessInit](/images/Training/10-Minute_Application/process%20init.PNG)  

6. You can now start designing the process. You will notice a purple circle on the workspace - this represents the starting point of your process. The tools available for you to use to design the process will be surrounding the purple circle. For our sample application, we will only be using two tools, but we encourage you to consult the complete list of process features [available in the user guide](/Developer_Guide/Development_Environment/Toolbox/Processes/Step_Design/).<br>
   ![Screen5_designer%20zoom](/images/Training/10-Minute_Application/Screen5_designer%20zoom.jpg)  

7. If at any point during your process design you find yourself unable to edit your process, it's possible that it has been "locked". This is done as a precaution against the accidental editing of a process. To unlock the process, click on the barred pencil and paper icon in the corner of the work area.<br>
   ![Locked](/images/Training/10-Minute_Application/locked.PNG)  

8. We now need to add steps to our process. Click on the yellow square tool from the tools surrounding the starting purple circle and drag it to the right. Notice that the tools move to the latest step in the process. Repeat this process three times (1+2+3) to create three steps in our process. Finish the process by clicking on the purple circle to drag an end point to the process (4). Rename each step by double clicking it and inserting the following text:<br>
   ![Workflow](/images/Training/10-Minute_Application/workflow.PNG)  

    Step 1: "Get FX rate from ECB"   
    Step 2: "Validation by the manager"   
	Step 3: "Write data to public spreadsheet"    

	Don't forget step (4)!  

9. Save your process by clicking on the disk icon under the process design tab. We encourage you to consult the complete list of the process design features [available in the user guide](/Developer_Guide/Development_Environment/Toolbox/Processes/Process_Design).<br>
   ![Save](/images/Training/10-Minute_Application/save.PNG)  
   You now need to return to the project tab, you can do this by using this shortcut:   
   ![Sauvegarde](/images/Training/10-Minute_Application/Sauvegarde.PNG)  

10. In the application, the end user will select a currency from a drop down list. Before creating the web interface, we need to create a custom list that will be used as a source for the drop down list in the web interface. We encourage you to consult the tips to follow to create a custom list [available in the user guide](/Developer_Guide/Development_Environment/Toolbox/Custom_Lists).<br>
    Click on **+ New** and then select **Custom list**.<br>   
    ![CL](/images/Training/10-Minute_Application/CL.PNG)  

11. Change the name of the list to **Currencies** (1), then add three items to the list by clicking on **Add Line**, and complete the **Label** and **Value** for the following currencies: EUR, USD, GBP (2). Then save by clicking on the disk icon (3).<br>   
    ![CurrencyList](/images/Training/10-Minute_Application/Screen11_custom%20list%20complete.jpg)    

12. Return to the project tab.<br>
    Please note that as you use different areas of the platform, you can navigate easily between the work tools (process builder, interface builder etc.) by using the tabs that will open at the top of the work area.<br>
    ![Screen11b](/images/Training/10-Minute_Application/Screen11b_project%20tab.jpg)  

13. To create the web interface, click on **+ New** and then select **Web interface**.<br>     
    ![WI](/images/Training/10-Minute_Application/WI.PNG)  

14. Add a title for the web interface (1) and then click on the **Design** tab (2).<br>   
    ![WI-Implementation](/images/Training/10-Minute_Application/WI%20-%20implementation.PNG)   

15. In the web interface **Widget Tool Box**, click on the **List** icon to add a list (1). Change the label to **Currency** (2) and select **Custom List** (3) as the list type.<br>
    ![CL-WI](/images/Training/10-Minute_Application/CL%20-%20WI.PNG)  

16. Then, click on **Choose a list** to view the pre-created custom lists. Choose the list "Currencies" that you created earlier and click **OK**.<br>   
    ![ChooseCL](/images/Training/10-Minute_Application/Choose%20CL.PNG)  

17. Save the web interface of your new application by clicking on the disk icon.<br>
    Note: a web interface consists of multiple screens that correspond to different groups of users and steps of the same process. In this example, a requestor selects a currency (from the launch screen) and a manager validates the exchange rate (on the validation screen). The first screen is always the launch screen at the beginning of the process.<br>   
    ![ShortcutProject](/images/Training/10-Minute_Application/shortcut%20project.PNG)  

18. A **Submit** button needs to be added that will launch the process when clicked. Firstly add a new widget zone to the launch screen by clicking on the **+**, select widget **Button** (1), change the label to **Submit** (2), and click **Choose a process** (3).<br>   
    ![AddWidget](/images/Training/10-Minute_Application/add%20widget.PNG)    
    ![Boutton](/images/Training/10-Minute_Application/boutton.PNG)  

19. Select the process that you created earlier, **Quick Currency App**, and click **OK**.<br>  
    ![SelectProcess](/images/Training/10-Minute_Application/select%20process.PNG)  

20. Next, we will create a second screen for this web interface that will correspond to the validation step of the process. To create a new screen click on the green **+**.<br>
    ![CreateNewScreen](/images/Training/10-Minute_Application/screen.PNG)  

21. Name your new screen **Validation** (1), and click **Add a new screen** (2).<br>   
    ![NewScreen](/images/Training/10-Minute_Application/new%20screen.PNG)      

22. You've now created a second screen. When you add a new screen to a web interface you may not necessarily want to see all elements of the first screen and you may want to add     others. To manage this, you can edit the visibility settings of each widget in the web interface. Managing different screens of the same web interface makes it possible to      share elements and variables of the process without having to re-create everything multiple times.<br>   
    In this example, the ** Currency** widget needs to be visible in the **Validation** screen, to facilitate this click on the currency widget (1), go to **Rules** tab (2), and tick **Visible** (3) and tick **Required**. By default, the **Submit** button is not visible. As this button isn't needed on the validation screen, it remains invisible. The **Submit** button is only visible on the launch screen.<br>
    ![VisibilityRules](/images/Training/10-Minute_Application/visibility%20rules.PNG)    

23. The second screen will be used to validate the FX rate, the FX rate therefore needs to be displayed on the screen. To place a new widget to the right of the **Currency** one click on **+** on the right margin of the Currency Widget (1).<br>    
    ![AddNumberInput](/images/Training/10-Minute_Application/add%20number%20input.PNG)<br>
    This will create a new widget zone on the right. Choose **Number Input** from the **Choose a Widget** window as this widget will be used to display the FX rate.<br>
    Change the label of this widget to be **FX rate** in the **Properties** tab.<br>
    ![FXRateVar](/images/Training/10-Minute_Application/FX%20rate%20var.PNG)  

24. Follow the same process to add a button to the bottom left of the web interface (1) then split the row (by clicking on the **+** on the right hand side of this zone) to make room for a second button. Select the first widget zone and change the label to **Validate** (2), put **choice** as a variable (3) and **validated** for value (4).<br>   
    ![ButtonValidation](/images/Training/10-Minute_Application/button%20validation.PNG)  

25. Click on the zone on the right and repeat the process, adding another button (1). Set the label of the new button to **Reject** (2), add **choice** as a variable (3) and **rejected** as the value (4).<br>   
    ![Reject](/images/Training/10-Minute_Application/reject.PNG)  

26. Click on the save icon to save your web form.<br>   
    ![Save](/images/Training/10-Minute_Application/save.PNG)   

27. Return to the **Process Tab** to configure the various steps of the process.<br>   
    ![ProcessTab](/images/Training/10-Minute_Application/tabprocess.jpg)  

28. Of the three steps in our process, two will use connectors (the first and third step) and one (the second step) will be a manual task. A manual task is a step that is assigned to a user role or to a specific person that he/she must manually complete in order to move forward in the process. We'll begin by configuring the 2nd activity as a manual task. Click on the second step in the process (1), then on the design icon (2), set the type to be **Manual** (3) and open the **Assign a manual task ** tab that is now visible.<br>   
    ![ManualTask](/images/Training/10-Minute_Application/ManualTask.jpg)  

29. Write **FX rate approval** in the title (1), then click on **Choose a web interface** (2), select **Quick Currency App** (3) and click **OK** (4). Return to the **Assign a manual task tab** and select **Validation** as the screen (5). Add **${P_initiator.login}** in the **Assign to field** (6); this is one of the standard RunMyProcess global variables that can be found in the [user guide]( /API_Reference/Internal_Parameters).<br>  
    Ensure that **Notify via email** is selected (7) and click **Choose a provider** (8). Expand the **Mail provider** project by clicking on the arrow sign (9), select **Default mail server** (10) and click **OK** (11). You may want to configure your own mail provider (see example with [Gmail provider](/Integration_Guide/Google/Mail)).<br> ![AssignManualTask](/images/Training/10-Minute_Application/2013-03-11_151039.png)   
    ![SelectWI](/images/Training/10-Minute_Application/select%20WI.PNG)   
    ![SelectProvider](/images/Training/10-Minute_Application/select%20provider.PNG)     
    Save your process.

30. Now you can proceed to configuring the first and third steps of the process which will both use connectors - the first to get the FX Rate from the European Central Bank and the third to write the data to a Google Spreadsheet.<br>  
    ![Process](/images/Training/10-Minute_Application/Process.png)   
    The first step is to import the required connectors from the library.<br>  
    Go to the **Libraries** tab and select **Connectors**.<br>    
    ![Libraries](/images/Training/10-Minute_Application/libraries.PNG)  

31. Click on the **Name** column to sort all connectors by name.<br>   
    ![ListeConnecteurs](/images/Training/10-Minute_Application/liste%20connecteurs.PNG)  

32. Find **European Central Bank** provider, expand it by clicking on the small arrow (1) and import the **Daily Euro Rate Exchange** connector by clicking on the **basket** icon next to the connector (2).<br>   
    ![EuropeanCentralBank](/images/Training/10-Minute_Application/European%20Central%20Bank.PNG)   

33. You now have the choice between importing the connector with its provider or attaching the connector to an existing provider.<br>
    Select the first option (3), import the provider into your existing project **Quick Currency App** (4) and click **Import** (5).<br>    
    ![33](/images/Training/10-Minute_Application/33.PNG)   
    Click **OK** when a pop-up window appears.<br>   
    ![SuccessImport](/images/Training/10-Minute_Application/success%20import.PNG)  

34. Return to the **Libraries** tab and select **Connectors**.<br>
    Remember that you can click on **Name** to sort the list alphabetically. Locate and expand the **RunMyProcess - CAPI Call** provider by clicking on the small arrow (1) and import **Training 10 min Application - Add row in a spreadsheet** connector by clicking on the **basket** icon (2).

35. Select **Import connector provider as defined in the library** (3), select your project **Quick Currency App** (4) and click **Import** (5).<br>    
    ![35](/images/Training/10-Minute_Application/35.PNG)  

36. As we will be writing data to a public spreadsheet, no authentication is required. We need to specify this in our provider. Click on the project tab (1), click on the down arrow next to Connectors (2) and click on the Google provider (3). We encourage you to consult the tips to set up your provider [available in the user guide](/Developer_Guide/Development_Environment/Toolbox/Custom_Lists).<br>
    ![36](/images/Training/10-Minute_Application/36.PNG)    
    Set the authentication scheme to be **None** across all three environments - Live, Acceptance and Test.<br>   
    ![36conf](/images/Training/10-Minute_Application/36%20conf.PNG)       
    Save your configuration.  

37. We are now ready to make use of our imported connectors in our process. Return to the process design tab.<br>   
    ![MenuConnector](/images/Training/10-Minute_Application/menu%20connector.PNG)  

38. The first step of our process gets the exchange rate from the European Central Bank, we therefore need to configure this step as a **Connector**:<br>
    Click on the first step of the process (1) and click on the design tool (2), choose **Connector** as the type (3). Click on the **Call a connector** tab that is now visible (4).<br>   
    ![RateFXConnector](/images/Training/10-Minute_Application/Rate%20fx%20connector.PNG)  

39. Click on **Choose a provider**.<br>   
    ![ChooseProvider](/images/Training/10-Minute_Application/choose%20provider.PNG)  

40. Select **European Central Bank** provider(1) and click **Ok** (2).<br>   
    ![40](/images/Training/10-Minute_Application/40.PNG)   

41. Click on **Search connector in the directory**.<br>   
    ![SetConnectorAddRow](/images/Training/10-Minute_Application/set%20connector%20add%20row_.PNG)  

42. A - Select **Daily Euro Rate Exchange** (1) and click **OK** (2).<br>  
    ![DailyEuroRate](/images/Training/10-Minute_Application/daily%20euro%20rate.PNG)  
    B - Get the result of the connector which is a JSON object with the list of all the currency with their rate if they are compared with a **based on 1 EUR**. The idea now is to get only the value of 1 euro in the currency selected. So we have to loop on the result with the currency value select by the requester. Two outputs have to be created:<br>
    (1) **currency**: ${currency_value?upper_case}<br>
    (2) **fx_rate**:  ${P_result.rate[currency]}<br>
    ![2011-07-26_161123](/images/Training/10-Minute_Application/2011-07-26_161123.jpg)   
    Don't forget to save each time you add things!

43. The third step in our process is to write the FX rate, the name of the user and the date to a Google spreadsheet. For this we will use the Google Spreadsheet connector that we imported from the library earlier.<br>    
    To configure the third activity as a **Connector**:<br>   
    Return to the process design tab. Click on the third step (1), click on the design tool (2) and click on the Functional tab and select **Connector** as the type (3). Click on the **Call a connector** tab that is now visible (4).<br>   
    ![ConfigureGoogleConnector](/images/Training/10-Minute_Application/ConfigureGoogleConnector.png)  

44. Click on **Choose a provider**.<br>   
    ![ChooseProvider](/images/Training/10-Minute_Application/ChooseProvider.jpg)

45. Select **RunMyProcess - CAPI Call** (1) and click **OK** (2).<br>
    ![Providers](/images/Training/10-Minute_Application/Providers.png)  

46. Click on **Search connector in the directory**.<br>   
    ![46](/images/Training/10-Minute_Application/46.PNG)  

47. Select **Training 10 min Application - Add row in a spreadsheet** (1) and click **OK** (2).<br>   
    ![47](/images/Training/10-Minute_Application/47.PNG)  
    Save your process design by clicking on the save icon.<br>    
    ![Add-SaveIcon](/images/Training/10-Minute_Application/Add%20-%20save%20icon.PNG)  

48. We have now configured the connectors that we will be using. The Google Spreadsheet connector will be expecting some input variables, these need to be configured to have the correct values. Click on the third step of the process (1), then click on the design tool (2) and open the **Input variables** tab (3). You'll see that the **input variables** have already been populated, these are the input parameters required by the connector. You need to update two of these variables:
    - **P_mode ⇒ ${P_mode}**
    - **currency_value ⇒ ${currency_value}**
    - **fx_rate ⇒ ${fx_rate}**
    ![49](/images/Training/10-Minute_Application/49.PNG)  

49. The exchange rate we obtain from the European Central Bank connector will be written, along with the name of the user and the date, to a Google Spreadsheet in step 1. To facilitate this, we need to capture the output data that will be written in the spreadsheet in case if we need to check the consistency of the data. To set up output variables for the third step, click on the pencil icon (step 2) and then click on “Output variables” and create the variable:
    - **spreadsheet_data ⇒ ${P_result}**<br>
    ![48](/images/Training/10-Minute_Application/48.PNG)  

50. Save your process by clicking on the save icon.    
    ![Save](/images/Training/10-Minute_Application/Add%20-%20save%20icon.PNG)  

51. Your first application is now ready to be tested. Go back to the web interface tab (1) and click **Open in Test mode** (2).<br>   
    ![51](/images/Training/10-Minute_Application/51.PNG)  

52. Select a currency (1) and click **Submit** (2).<br>   
    ![52](/images/Training/10-Minute_Application/52.PNG)  

53. The process has been triggered in the background. You should receive an email notifying you that a manual task has been assigned to you. Go to your mailbox, open the email (1) and click on the task link (2) (if you can't find it in your inbox, check your SPAM folder).<br>   
    ![FXRateApproval](/images/Training/10-Minute_Application/FX%20Rate%20Approval.PNG)     
    ![FXRateApprovalMail](/images/Training/10-Minute_Application/FX%20Rate%20Approval%20-%20Mail.PNG)   

54. You can edit the value of the FX rate (1) if you want to, then click **Validate** (2).<br>   
    ![54](/images/Training/10-Minute_Application/54.PNG)  

55. Your workflow process has been successfully updated. If the project is functioning properly, you should be able to see a new row with your name in [this spreadsheet.](https://docs.google.com/spreadsheets/d/1-Cj-e1JGs1mjQphYiYx0j19ei1_aCVEYnPQ0Exa3QIk/edit#gid=0)  

56. **If there is an error or a mistake in the project** (for example if you didn't receive the email or you don't see your name in the spreadsheet), go back to your project, click on **New**, then select **Report** and select **Process report**.<br>   
    ![56](/images/Training/10-Minute_Application/56.PNG)   
    Next, select **Test** mode (1) and click **Search results** (2).   
    ![56-bis](/images/Training/10-Minute_Application/56%20-%20bis.PNG)   
    You should see the following window :   
    ![56-ter](/images/Training/10-Minute_Application/56%20-%20ter.PNG)   
    The two red dots next to the processes indicate process errors. We encourage you to consult how to use the process report [available in the user guide](/Developer_Guide/Development_Environment/Toolbox/Custom_Lists).<br>
    To investigate the errors, click on the request (1) to see the steps of the process that retrieve an error as well as the error message at the bottom of the screen:   
    ![56-quatre](/images/Training/10-Minute_Application/56%20-%20quatre.PNG)  

57. Also, if you click on the “@ Parameters” tab, it will allow you to display the variables used and passed on by the process during execution.<br>
    **Initial parameters** - These parameters are sent to the process on launching.<br>
    **Computed parameters** - These parameters are calculated during process execution with their current values.<br>
    **Internal parameters** - These parameters are generated and used by RunMyProcess during execution.<br>
    You can find the values of P_result (result of a task), P_task (id of last task executed), P_user (user who has performed the latest action on the process).<br>
    If you are facing an error it will give you an idea of its nature. Otherwise, it will give you an overview of the variable values.<br>

58. To consult the test web interface in the future, open your project and click on the **Launch** icon (1), then click **Test** (2) and select **Last revision** (3).<br>    
    ![57](/images/Training/10-Minute_Application/57.PNG)  

**Congratulations! You've made your first RunMyProcess application!**
**[Was this tool helpful to you?](http://www.surveygizmo.com/s3/627699/Feedback-Create-a-RunMyProcess-App-in-10-minutes)**
