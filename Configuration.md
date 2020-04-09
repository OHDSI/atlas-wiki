# Configuration

Select the "configuration" menu item to review the data sources that have been configured in the source configuration section. This screen will let you review options. At this time, it cannot be used to edit the configuration  - that must be done directly in the database.

<img src="images/configuration/atlas_configuration.png">

## Adding Data Sources

Data sources can be added to the ATLAS web application from the Configuration page.  If needing to bulk load data sources, this can be done by connecting to the ATLAS application database.

### Web Application
To add data via the web application please follow the instructions below:

1. Click on 'New Source' in the top right corner.

2. Complete the 'New Source' form by adding the following:
    + New Source:  User friendly name for the data source.
    + Source Key:  A unique name/identifier for the data source.  No spaces allowed.  
    + Source Dialect:  Type of database you will be configuring.
    + Connection String:  String that will allow the ATLAS application to connect to a data source.  A Redshfit example of this string is included here for your reference (jdbc:redshift://[serverName]:5439/[databaseName]?ssl=true&sslfactory=com.amazon.redshift.ssl.NonValidatingFactory)
    + Username:  System account that ATLAS will leverage to connect and run all queries.
    + Password:  Password associated with your 'username'.
    + Source Daimons:  Pointers to schemas so that ATLAS understands where to look for certain information and how to execute speicific queries.
      + CDM:  Database schema name that contains your CDM tables
      + Vocabulary:  Database schema name that contains your vocabulary tables (often times this is the same schema as your cdm schema)
      + Results:  Database schema where the results of cohorts and analyses will be stored.  (NOTE:  Connecting multiple results ATLAS Web API's to the same results schema may lead to database / schema corruption.  Recommend one results schema per ATLAS WebAPI instance)
      + CEM:
      + CEMResults:
      + Temp:  This database schema stores temporary tables leverage for different features within ATLAS (e.g. the Characterization feature will temporarily store data here prior to completing.)
3. Once the 'New Source' form has been completed, click the green save button.
4. Users will find themselves on the Configuration page.  To check that your connection is working properly, click the 'Check' button under the 'Check Connection' column.
  
### Database (bulk load option)
For more information on this process, please visit:  https://github.com/OHDSI/WebAPI/wiki/CDM-Configuration.  One key point to note is that for a data source to be fully configured records must be inserted into both the source and source_daimon tables.