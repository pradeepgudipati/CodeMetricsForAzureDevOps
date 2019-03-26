# Code Metrics For Azure DevOps
A Simple extension for showing code metrics on the git repositories of Azure DevOps 

## This extension provides a simple overview of the statistics for the repos under your project

### Sample Report

### Total Commits per user
| Name | Total Commits |
| ------ | ------ |
|Developer 1|	25|
|Developer 2|	34|
|Developer 3|	39|

### Git Stats per User
| Name | Total Adds | Total Deletes | Total Edits |
| ------ | ------ |------ |------ |
|Developer 1|	257|	50|	125|
|Developer 2|	34|	25|	25|
|Developer 3|	39|	25|	25|

### Total PRs per user

| Name | Total PR's |
| ------ | ------ |
|Developer 1|	25|
|Developer 2|	34|
|Developer 3|	39|

### Other Stats
Total PRs' = 65
Average Age in minutes = 653


- ## Setup Code 
  1. Go to Project Root folder via bash/command line 
  2. Run npm install. 

- ## Build
    ### To build the extension.
    #### Manual Upload.
  1. Update the version number in the vss-extension.json
  2. Build the extension. 
    ```shell 
         tfx extension create --manifest-globs .\vss-extension.json
    ```
  3. Follow Step 3 of `Publish` below

  4. To build and publish the extension directly
    ```shell
        tfx extension publish --rev-version --share-with <project name> --token <token here>
     ```
- ## Publish  
    1. Go to the Publisher Site 
    ```url
    https://marketplace.visualstudio.com/manage/publishers/<PublisherID>
    ```
    The above publisher id should also be present in the `vss-extension.json` file. 
    ```json 
      "publisher": "???",
    ```

    2. If you are doing it the first time Click on 
        - "+" New Extension 
        - Select Visual Studio Team Services 
        - Drop the ***. vsix file in the window

    3. Otherwise 
        - Click on the `...` next to the Extension in the list 
        - Select the Update option in the context menu 
        - Drop the updated *.vsix file into the window. 
        - Remember to update the version number before performing the Build Step. 


- ## Authorization for Domain 

Once the Extension is installed and enabled in your domain Go to the below link to enable & authorize this extension

```url
 https://dev.azure.com/<org name>/_settings/extensions?tab=Manage&status=active
```
