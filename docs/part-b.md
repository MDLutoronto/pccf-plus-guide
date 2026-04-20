---
title: Part B. Adding your dataset and census data
parent: PCCF+ Guide
nav_order: 2
layout: default
---

Part B. Adding your dataset and census data
-------------------------------------------

#### **In this section of the guide, we will add your dataset and census data to our final dataset from part A.**

1. Our final dataset from part A is [mypostalcodespccfp.csv](https://maps.library.utoronto.ca/workshops/PCCF/mypostalcodespccfp.csv). Our dataset is [My_dataset.csv](https://maps.library.utoronto.ca/workshops/PCCF/My_dataset.csv). Now we need to download our census dataset.

    We can download the census dataset from the CHASS Data Centre website. To access the data from CHASS, you will need to login using your UTORid using the following link: [https://login.library.utoronto.ca/index.php?url\=http://dc.chass.utoronto.ca/](https://login.library.utoronto.ca/index.php?url=http://dc.chass.utoronto.ca/)

    <img src='{{ '/assets/images/PCCFPlus_B_001.png' | relative_url }}' alt='A screenshot of a web-page. The title reads: Connect to this resource using your UTORid. This resource is licensed for your use by the University of Toronto Libraries. Off-campus access is available to current University of Toronto students, staff and faculty. At the bottom is a blue button that says: Log in with your UTORid. ' title='' width='75%' height='551' />

2. After you login, you will be directed to the CHASS Data Centre homepage. From the menu on the left\-hand side, select Canadian Census.

    <img src='{{ '/assets/images/PCCFPlus_B_002.png' | relative_url }}' alt='The homepage for CHASS Data Centre.' title='' width='75%' height='594' />

3. This will take you to the Census Analyser page. We will need to select the census profiles by census year and census geography. We will select our census profiles by census year first for this guide. Select 2016 under by Census Year.

    <img src='{{ '/assets/images/PCCFPlus_B_003.png' | relative_url }}' alt='A website page from the CHASS Analyser. The title reads: Welcome to the Canadian Census Analyser. Under the title is a list of Starting Points. There are two sections under Census Profile Tables: by Census Geography; by Census Year. Under by Census Geography are a list of hyperlinks labelled: Canada, Provinces, and Territories; Federal Electoral District; Forward Sortation Areas (FSA); Census Division; Census Subdivision; Census Tract; Enumeration area/Dissemination area. Under by Census Year there are a list of hyperlinks labelled: 2016; 2011 NHS; 2011; 2006; 2001; 1996; 1991; 1986; 1981; 1971; 1961. ' title='' width='65%' height='1920' />

4. Then we select the census geography. Select Profile of Dissemination Areas.

    <img src='{{ '/assets/images/PCCFPlus_B_004.png' | relative_url }}' alt='A website page from the CHASS Analyser. There are a list of hyperlinks to Census Profiles. The list is as follows: Profile of Canada, provinces, territories; Profile of Census Divisions; Profile of Census Subdivisions; Profile of Dissemination Areas; Profile of Aggregate Dissemination Areas; Profile of Census Metropolitan Area and Census Agglomerations; Profile of Census Tract' title='' width='65%' height='1837' />

5. This will direct you to a page where you can make additional choices to make your census profile table. In step 1, you can select a subset of regions or select all. For this guide, we will select “check all”.

    <img src='{{ '/assets/images/PCCFPlus_B_005.png' | relative_url }}' alt='A website page from the CHASS Analyser. The title reads: Step1: Specify Census Geography for retrieval. The tab by Name is selected. Underneath is a list of all letters of the alphabet. All letters are selected. ' title='' width='65%' height='1165' />

6. In step 2, you can select the census variables that you are interested in. (Note: you may need to scroll way down the page before you see step 2). The variables are grouped by topic under the topic tabs (eg. Population and dwellings, Age & sex etc). You will find the list of variables under the tabs. To select a variable, click on the check box to the left of the variable description.

    <img src='{{ '/assets/images/PCCFPlus_B_006.png' | relative_url }}' alt='A website page from the CHASS Analyser. The title reads: Step2: Specify Census Profile variables for retrieval. Underneath is the option to select Census Profile Variables. The Income tab is selected. Under Income - Total Sex, the option Median total income in 2015 among recipients ($) (v1868) is selected.' title='' width='70%' height='1235' />

    For this guide, we select the following four variables:

    1. Income - Total Sex / Total - Income statistics in 2015 for the population aged 15 years and over in private households - 100% data / Number of total income recipients aged 15 years and over in private households - 100% data / Median total income in 2015 among recipients ($) (v1868\)
    2. Housing - Total Sex / Total - Owner households in non-farm, non-reserve private dwellings - 25% sample data / Median monthly shelter costs for owned dwellings ($) (v3942\)
    3. Education - Total Sex / Total - Highest certificate, diploma or degree for the population aged 15 years and over in private households - 25% sample data (v4920\)
    4. Education - Total Sex / Total - Highest certificate, diploma or degree for the population aged 15 years and over in private households - 25% sample data / Postsecondary certificate, diploma or degree / University certificate, diploma or degree at bachelor level or above (v4929\)

7. In step 3, you can select the geographic variables to be included in the census dataset and the output data format to download the census dataset.

    Check all 5 of the geographic variables. In the *Select the output format* box, under *Download to a file*, we select *Comma\-Separated Values (CSV) file for spreadsheet* to download the census dataset as a CSV file. Select Submit Query.

    <img src='{{ '/assets/images/PCCFPlus_B_007.png' | relative_url }}' alt='A website page from the CHASS Analyser. The title reads: Step3: Specify the output details and submit query. Under Output details, all options are selected. At the bottom, there is a section titled: Census variables to be listed as: (apply only to Screen output format). The columns option is selected. ' title='' width='80%' height='1065' />

    <img src='{{ '/assets/images/PCCFPlus_B_008.png' | relative_url }}' alt='A section of the CHASS Analyser Output screen. The title reads: Select the output format. Under the title is a box with options for Screen output and the option to Download to a file. The option Comma-Separated Values (CSV) file for spreadsheet is selected. ' title='' width='70%' height='1204' />

    The wizard might take a few minutes to complete the query. When the data request is complete, you will be provided with two links. One to download the data file and another one to download a file with descriptions of the column names in the first data file.

    Right-click on the link next to Data file to download the census dataset. Choose Save Link As… We save this data file as census2016\.csv.

    <img src='{{ '/assets/images/PCCFPlus_B_009.png' | relative_url }}' alt='A website page from the CHASS Analyser. The title reads: Data Centre Download Status. Underneath it lists the Data Request Summary. It gives the option to download the files. There is a link for the Data file and a link for the Header file.' title='' width='80%' height='1501' />

    Now that we have downloaded the census dataset, we have all three data files ready: My_datatset.csv (our dataset), mypostalcodespccfp.csv (our data from part A), and census2016.csv (our census dataset).

    We want to enrich the data from part A with our dataset and census data. We will continue to use SAS to combine these three datasets. The code we will run in SAS is described below.

8. In SAS, we open a new editor: go to the File menu>select New Program. We will type the SAS code in the new editor.

9. First, we import our three data files using the following SAS code. The code renames these datasets mydataset, mypostalcodespccfp and census respectively in the context of SAS.

    Type and run the code below. Make sure that you modify the file paths to point to those three data files on your computer.

    ---

    ```
    * PCCF+ Guide; 
    * PART B: Adding your research dataset and census data; 

    * Instruction: 
    * - Replace the data file paths below with the respective file paths on your computer;

    * STEP 1: Importing datasets

    * Import your dataset; 
    proc import out=work.mydataset
                datafile="H:\PCCF Guide\Data\My_dataset.csv"
                dbms=csv replace;
      getnames=yes;
      datarow=2;
    run;
    ```

    ---

    ```
    * Import data from part A - your postal codes combined with the PCCF+ file;
    proc import out=work.mypostalcodespccfp
                datafile="H:\PCCF Guide\Data\mypostalcodespccfp.csv"
                dbms=csv replace;
      getnames=yes;
      datarow=2;
    run;
    ```

    ---

    ```
    *Import the census data file;
    proc import out=work.census
                datafile="H:\PCCF Guide\Data\census2016.csv" 

                dbms=csv replace;
      getnames=yes;
      datarow=2;
    run;
    ```

    ---

10. To run or execute this code, highlight all of these lines of code and click the running man icon on the toolbar![](data:image/png;base64,iVBORw0KGgoAAAANSUhEUgAAABUAAAAUCAIAAADtKeFkAAAAAXNSR0IArs4c6QAAAIdJREFUOE/Vk0sOwCAIRGtPLien4CSkkY8mbloWjaG8YSDamPk6iPuAVfTLPBG1EXLIxtzy33vP+FbvX5oLWdTE/c15Dasp0Z7Cu0VGvr444K30PXMI61xeEhlzkRUgn/LWPOsMPt4/1m5jV1uc7Pm2UMmmmH+Ee4ZoKLG4P8vXuXV/C5W/8w8cOkMXxliUdQAAAABJRU5ErkJggg==).

11. Then we combine mydataset and mypostalcodespccfp. We need to prepare these two datasets before we can combine them using the SAS code below.

    We rename the postal_code variable in mydataset to pcode to match the variable in mypostalcodespccfp dataset.

    The postal codes in the pcode variable in mydataset have a single space between the first three characters or the forward sortation area and the last three characters or the local delivery unit. We remove this space to match the postal codes in mypostalcodespccfp.

    ---

    ```
    * STEP 2: Combine the datasets mydataset and mypostalcodespccfp;

    * Rename the postal code variable in your dataset pcode;
    data mydataset; set mydataset; rename postal_code=pcode; run;
    ```

    ---

    ```
    * Remove the single space in pcode in mydataset;
    data mydataset; set mydataset; pcode = compress(pcode); run;
    ```

    ---

12. We combine mydataset and mypostalcodespccfp by matching the value of the postal codes. To merge two datasets in SAS, you need to sort each dataset by the merging variable first.

    Use the SAS code below to sort each dataset by pcode and then merge mydataset and mypostalcodespccfp. We name the merged dataset mydatasetpccfp.

    ---

    ```
    * Sort each dataset by the pcode variable;
    proc sort data=mydataset; by pcode; run;
    ```

    ---

    ```
    proc sort data= mypostalcodespccfp; by pcode; run;
    ```

    ---

    ```
    *Merge: combine the two datasets by matching the postalcode variable;
    data mydatasetpccfp;
        merge mydataset mypostalcodespccfp;
        by pcode;
    run;
    ```

    ---

13. We have successfully added our dataset. In the third step, we want to add the census data: we want to combine mydatasetpccfp and census by matching the value of the dauid variable.

    We need to prepare these datasets before we can combine them using the SAS code below. We rename the col0 variable dauid in the census to match mydatasetpccfp. Then, we convert this variable from character to numeric to match the data type of the dauid variable in mydatasetpccfp.

    ```
    * STEP 3: Combine the datasets mydatasetpccfp and census; 

    * Rename the variable col0 dauid in the census dataset to match mydatasetpccfp; 
    data census; set census; rename col0=dauid; run; 
    ```

    ---

    ```
    *Convert the data type of dauid from character to numeric in the census to match mydatasetpccfp;
    data census; set census; dauid2 = input(dauid, 10.); drop dauid; rename dauid2=dauid; run;
    ```

    ---

14. To merge mydatasetpccfp and census, we sort each dataset by dauid first. Then we merge these two datasets by matching the value of dauid. We name the merged dataset mydataset2\.

    The census dataset is much larger than mydatasetpccfp because it contains dissemination areas from all over Canada outside of the regions in our dataset. Since we are not interested in these additional dissemination areas, we add some additional code in the merge step to keep only the dissemination areas that are part of mydatasetpccfp.

    ```
      * Sort each dataset by the dauid variable; 
    proc sort data=mydatasetpccfp; by dauid; run; 
    ```

    ---

    ```
    proc sort data=census; by dauid; run; 
    ```

    ---

    ```
      * Merge: combine the two datasets by matching the dauid variable and only keep your DAs; 
    data mydataset2; 
        merge mydatasetpccfp (in=x) census; 
        by dauid; 
        if x=1; 
    run; 
    ```
15. In the last step, we export our final dataset. We define a library by specifying a path to our output folder. Then we export mydataset2 as a SAS data file and a CSV data file.

    ```
    * STEP 4: Export mydataset2; 

    * Create a libname to point to your output folder; 
    libname folder "H:\PCCF Guide\Data"; 
    ```

    ---

    ```
    * Save mydataset2 as a SAS dataset in your output folder; 
    data folder.mydataset2; set work.mydataset2; run; 
    ```

    ---

    ```
    * Export mydataset2 to CSV in your output folder; 
    proc export data=work.mydataset2
                outfile="H:\PCCF Guide\Data\My_dataset2.csv" 
                dbms=csv replace; 
    run; 
    ```
    The complete SAS code file to add our dataset and census data can be downloaded [here](https://maps.library.utoronto.ca/workshops/PCCF/PCCF+%20SAS%20code%20-%20Part%20B.sas).

**Technique:** [Quantitative Data Analysis](https://mdlutoronto.github.io/tutorials-search/?technique=Quantitative+Data+Analysis) | Tools: [R](https://mdlutoronto.github.io/tutorials-search/?tool=R), [SAS](https://mdlutoronto.github.io/tutorials-search/?tool=SAS), [SPSS](https://mdlutoronto.github.io/tutorials-search/?tool=SPSS) | Data Format: [Microdata](https://mdlutoronto.github.io/tutorials-search/?dataFormat=Microdata)
