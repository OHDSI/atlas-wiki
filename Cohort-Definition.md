# Defining Cohorts

TODO: Add screen shots and expand on original wiki article.

When performing an analysis, usually the first step is to define the population of interest known as a cohort.  

## Browsing cohorts =====

Select the "cohorts" menu option to browse existing cohorts. Click on an existing cohort to dive into the cohort definition and other functions that will be described in the subsequent sections. Alternatively, you can select the "New Cohort" button in the top-right of the screen to create a new one.

You can use the table to browse through existing cohort definitions. The filter functionality above the table can be used to filter the list based on a search string. Furthermore, the columns in the table can be used to sort the information in the table to find the cohort(s) of interest.

## Cohort Definition (Under construction)

A cohort can be created and may contain for example users of a given drug, people with a specific outcome or some combination of both. Cohorts can be created by clicking on the Cohorts menu item and then the blue New Cohort button in the upper right hand side of the page. Or you can click the "Define a New Cohort" button from the home page.

Your cohort will initially be titled 'New Cohort Definition,' as seen in the text field at the top of the screen. Please rename your new cohort in a unique, descriptive manner and hit "Save". Note, your cohort will always remain open as your current working cohort, seen on the top left of the main contents frame, until you hit 'Close.' You will have to close any open cohort before creating a new cohort.

Please carefully read the paragraph regarding Cohort Definition, which explains what a cohort is and what criteria are needed to define a cohort. You will then need to select and define the Cohort Entry Criteria (Initial Event, Initial Event Inclusion Criteria, and Additional Qualifying Inclusion Criteria). You may also choose to define Cohort Exit Criteria and Censoring Events but these are not required or may not apply to your cohort. 

Please read and follow the instructions closely on how to define each criteria and select the appropriate time windows. Most criteria (except for Demographics) will require you to import concept sets in order to utilize the vocabulary to properly identify your criteria. You can further refine each criteria with additional criteria attributes on the right side of the screen. If you have not previously created your concept set, you can click the 'New Concept Set' button once the import concept set window appears. Once you have filled in all your desired criteria, you have finished building your cohort.


## Concept Sets

The concept sets tab will list the concept sets that are defined within the cohort. To review the definition of the concept set you can select it from the table and the definition will show up below it. The concept set definition will be shown and takes the same form as described in the Concept Set section. Furthermore, the cohort concept set that has been opened will now appear in the left hand menu as the current concept set. 

## Generation

When you feel that your cohort definition is complete, you can use the Generate tab to generate a list of people in your cohort. This tab will show a table of CDM data sources that are available with the following properties:

  * **Generate button**: clicking this button will execute SQL code against your CDM to select people that will define your cohort.
  * **Source Name**: the source name of your CDM
  * **Generation Status**: This will show the status of the cohort generation activity
  * **Distinct People**: If the cohort has been generated, this will show the distinct number of people in the cohort
  * **Generated**: The date and time the cohort was generated
  * **Generation Duration**: How long it took to generate the cohort

Once this cohort is generated, you can use the reporting section to obtain further descriptive analytics around this cohort.

## Reporting

The reporting tab provides cohort summarization and visualization tools. 

From the reporting tab, you will see a column with the reports that are defined in the Heracles Analysis List section of this [article](http://www.ohdsi.org/web/wiki/doku.php?id=documentation:software:heracles).  Then you will see a column for each CDM source that has been defined. From here you can select each report by placing a check mark in the column and select the Generate button to generate the reports. This will start an analysis job that you can monitor by selecting the "Jobs" menu item.

Once the analysis is complete, each report will have a "view" button that you can use to view the results. 

### Drilldown reports

Some reports contain a top level set of statistics with the ability to drill into the details. More specifically, these reports are: Condition, Condition Eras, Drug Eras, Drug Exposure, Drugs by Index, Procedure and Procedures by Index. 

These reports contain an initial visualization with two tabs: treemap and table. The treemap provides a visualization of the data that appears on the table tab. The table tab provides a tabular view of each report. Clicking on a row in the tabular format OR on a cell in the treemap will reveal further details for the selected concept.

## Export

This tab provides a human-readable description of the cohort definition. This is useful when describing the logic used to define the cohort along with the concept sets/source codes that make up the definition. 

### How to copy an existing cohort/JSON =====

The JSON tab provides JavaScript Object Notation (JSON) representation of the cohort definition and supporting concept sets. This enables you to copy & paste the full cohort definition to provide as part of your study write up or to another member of the OHDSI network to generate the same cohort in their environment.

To copy an existing cohort, click the Cohort button on the left menu, and select the cohort you would like to copy. Within the cohort of interest select the Export tab, click the JSON button, click in the box, click the Ctrl + A keys simultaneously, and then Ctrl + C keys simultaneously. You've now copied the JSON code for the cohort. To create your local copy of the cohort, navigate to your local ATLAS site, click the Cohort button on the left menu, click create the New Cohort blue button in the upper right hand corner of the page. Click the Export tab, click the JSON button, click in the box, remove all of the text in the box by selecting and hitting the Delete key, and then click the Ctrl + V keys simultaneously, and click the Reload button. You've now just created your new cohort and should see the cohort definitions, concept sets, etc within the new cohort. Don't forget to name your new cohort and click the blue Save button just outside the cohort name box.


### Show SQL


The "Show SQL" button will provide a dialog that will show you the SQL statement that is executed based on the cohort definition. This window will allow you to copy/paste SQL from Atlas into a SQL editor for further refinement. This window will also provide the SQL for the different SQL dialects currently supported.
