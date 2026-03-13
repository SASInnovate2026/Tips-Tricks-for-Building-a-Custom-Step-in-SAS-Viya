# Tips & Tricks for Building a Custom Step with SAS Viya
* [Exercise Description](#exercise-description)
* [Log in to SAS Viya](#log-in-to-sas-viya)
* [Top 10 Tips \& Tricks for Building a Custom Step](#top-10-tips-tricks-for-building-a-custom-step)
  * [1. Review the Custom Step Sample Controls](#1-review-the-custom-step-sample-controls)
  * [2. Review the Custom Step Starter Templates](#2-review-the-custom-step-starter-templates)
  * [3. Search the Custom Step GitHub Repository](#3-search-the-custom-step-github-repository)
  * [4. Quickly Test the Custom Step using Stand-alone Mode](#4-quickly-test-the-custom-step-using-stand-alone-mode)
  * [5. Review the Log for Macro Variable Names and Values](#5-review-the-log-for-macro-variable-names-and-values)
  * [6. Use the New Column Control (if your code creates a new column)](#6-use-the-new-column-control-if-your-code-creates-a-new-column)
  * [7. Use Port Details to Control the Output Columns](#7-use-port-details-to-control-the-output-columns)
  * [8. Use **%let** and **%put** Statements to Aid in the Testing of your Code](#8-use-let-and-put-statements-to-aid-in-the-testing-of-your-code)
  * [9. Use **%global** Statement to Assign Macro Variable Values for Use Outside of the Custom Step](#9-use-global-statement-to-assign-macro-variable-values-for-use-outside-of-the-custom-step)
  * [10. Create an **About** tab for the Custom Step](#10-create-an-about-tab-for-the-custom-step)
* [Exercise Completed](#exercise-completed)

<br>

## Exercise Description
In this hands-on exercise, you will review the top 10 tips and tricks for creating a custom step in SAS Studio.

<br>
<br>

## Log in to SAS Viya

Open a new window in the *Google Chrome* browser and select the **SASLanding** bookmark.

* ID: **student**
* Password: **Metadata0**

Select **No** when prompted about accepting *Admin* privileges.

<br>

## Top 10 Tips & Tricks for Building a Custom Step

### 1. Review the Custom Step Sample Controls
1. Select ![Viya Menu Selector](images/HamburgerMenu.png) **&#10132; Develop Code and Flows** to open *SAS Studio*.
1. Select ![Steps Pane](images/Steps.png) to view the **Steps** pane.
1. Click **x** to close the *Start Page*.

    ![SAS Studio Steps page](images/SAS_Studio_Steps.png)

1. On the *Steps* pane, select ![New Custom Step and Examples](images/New_CS.png) **&#10132; Sample controls**.

    ![Open Sample Controls](images/SampleControlsMenu.png)

1. On the *Design* tab, select **Data** in the *Control Library* section to view the *Data* page of the *Sample Controls* custom step.

    ![Sample Controls Data tab](images/SampleControlsData.png)

    > &#9998; There is an example and text explanation for each of the **Data** controls with the exception of the *Output Table* data control.  There is an example and text explanation of that control on a another page.

1. Select **Controls** in the *Control Library* section to view the *Controls* page of the *Sample Controls* custom step.

    ![Sample Controls Controls tab](images/SampleControlsControls.png)

    > &#9998; There is an example and text explanation for each of the **Common** controls.  Select **>** to expand the control to view each example and text explanation.

1. Select **Dependencies** in the *Control Library* section to view the *Dependencies* page of the *Sample Controls* custom step.

    ![Sample Controls Dependencies tab](images/SampleControlDependencies.png)

    > &#9998; There is an example and text explanation for dependencies with *check box*, *number field*, and *drop-down list*.  Select **>** to expand the control to view each example and text explanation.

1. Select **Output** in the *Control Library* section to view the *Output* page of the *Sample Controls* custom step.

    ![Sample Controls Output tab](images/SampleControlsOutput.png)

    > &#9998; There is an example and text explanation for **Output table** *Data* control.

1. Click **x** to close the *Sample Controls.step* tab.

<br>

### 2. Review the Custom Step Starter Templates
1. On the *Steps* pane, select ![New Custom Step and Examples](images/New_CS.png) **&#10132; Starter tamplates &#10132; Basic - Rank**.

    ![Starter Template Basic - Rank](images/StarterTemplateBasic.png)

    > &#9998; There are also more complex *starter template* examples to review; however, for this exercise you will focus on the basic example.

1. Select the **Select and input table** control to view its properties.

    ![Input Table Control](images/RankInputTableControl.png)

    > &#9998; The property *ID* for the control is **inTable**.

1. Select the **Add a numeric column** control to view its properties.

    ![Numeric Control](images/RankNumbericControl.png)

    > &#9998; The property *ID* for the control is **rankBy**.

1. Select the **Specify the output table** control to view its properties.

    ![Output Table Control](images/RankOutputTableControl.png)

    > &#9998; The property *ID* for the control is **outTable**.

1. Select the **Create a new column for the ranked column** *check-box* control to view its properties.

    ![Check-box Control](images/RankCheckBoxControl.png)

    > &#9998; The property *ID* for the control is **createNewVariables**.

1. Select the **Program** tab to view the code for the custom step.

    ![Rank Program](images/RankProgram.png)

    > &#9998; The property *ID* references for the various controls from the user interface design for the custom step.

1. Click **Launch** to test the sample custom step in stand-alone mode.

    ![Launch Rank Custom Step](images/LaunchRank.png)

1. Make the following selections: <br>
    - Select an input table: **SASHELP.BASEBALL**.  <br>
        > &#9998; Click ![Input Table selector](images/InputTableSelector.png) to navigate to the desired input table. <br>
    - Select a column to rank: **CrHits** <br>
        > &#9998; Click ![Add column](images/AddColumn.png) to select a numeric column from the input table. <br>
    - Specify an output table:  **WORK.RANK_TEST** <br>
        > &#9998; Click ![Output Table selector](images/OutputTableSelector.png) to navigate to the desired output library and then enter the desired output table name. <br>
    - ![Checked Box](images/CheckedBox.png) Create a new column for the ranked column

1. Click ![Run button](images/RunButton.png) to run the custom step.

    ![Run Rank custom step](images/RunRankCS.png)

1. Select the **Output Data (1)** tab to view the resulting output from the custom step.

    ![Rank Output Table](images/RankOutputTable.png)

1. Click **x** to close the *Rank - Basic 1* tab.
1. Click **x** to close the *Rank-Basic.step* tab.
1. Select **Don't Save** if prompted when closing the tab.

<br>

### 3. Search the Custom Step GitHub Repository
1. Open a new tab in the *Google Chrome* browser.
1. Select **Learning Labs &#10132; SAS Studio Custom Steps** to open the SAS GitHub repository for custom steps.

    ![Access the SAS Studio Custom Steps GitHub repository](images/OpenGitHubRepo.png)

    > &#9998; This is the link to the SAS Studio Custom Steps GitHub repository: <br>
    <a href="https://github.com/sassoftware/sas-studio-custom-steps" target="_blank">https://github.com/sassoftware/sas-studio-custom-steps</a>.

1. Scroll down towards to the bottom of the page to view the **README** information for the repository.
1. Select the link for **List of custom steps in this repository**.

    ![Custom Step Repository README](images/CustomStepRepoREADME.png)

1. Scroll down until you locate the entry for **GeoDistance with Rounding** in the table of *Available Custom Steps*.

    ![List of Custom Steps](images/CustomStepListing.png)

1. Select the link for **GeoDistance with Rounding** to view additional descriptive information about the custom step.
1. On the left-hand side in the *Files* section, select the **GeoDistance with Rounding.step**.

    ![Select the custom step file](images/SelectCustomStepFile.png)

1. Click ![Download](images/DownloadGitHubFile.png) to download the file for this custom step.

    ![Download the custom step file](images/DownloadCustomStepEntry.png)

1. xxxx
1. xxxx
1. Return to the **SAS Studio** tab in the *Google Chrome* browser.
1. xxxx


<br>

### 4. Quickly Test the Custom Step using Stand-alone Mode
1. x

<br>

### 5. Review the Log for Macro Variable Names and Values
1. x

<br>

### 6. Use the New Column Control (if your code creates a new column)
1. x

<br>

### 7. Use Port Details to Control the Output Columns
1. x

<br>

### 8. Use **%let** and **%put** Statements to Aid in the Testing of your Code
1. add %put statement

<br>

### 9. Use **%global** Statement to Assign Macro Variable Values for Use Outside of the Custom Step
1. add %global statement

<br>

### 10. Create an **About** tab for the Custom Step
1. view **About** tab.

   > &#9998; To create a new page for an *About* tab, select ![Add Page button](images/AddPageButton.png) in the **Control Library** section on the *Design* tab for the custom step.

<br>

## Exercise Completed
You have completed the exercise for **Tips & Tricks for Building a Custom Step with SAS Viya**.

**THANK YOU FOR ATTENDING THIS SESSION!** <br>
**PLEASE COMPLETE THE EVALUATION!**