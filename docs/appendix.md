---
title: Appendix
parent: PCCF+ Guide
nav_order: 3
layout: default
---

Appendix
--------
[R Code](#r-code)  
[Stata Code](#stata-code)  
[SPSS Code](#spss-code)  
[Python Code](#python-code)

The R, Stata, SPSS and Python codes to accomplish the steps in part B (enriching your postal codes/pccf\+ with your dataset and census data) can be found below. The datasets used in the code are [My\_dataset.csv](https://maps.library.utoronto.ca/workshops/PCCF/My_dataset.csv), [mypostalcodespccfp.csv](https://maps.library.utoronto.ca/workshops/PCCF/mypostalcodespccfp.csv) and census2016\.csv. You need to follow the instructions in part B to download the census dataset.

Key points to keep in mind about these statistical programs:

* R, Stata, SPSS and Python are case sensitive.
* In SPSS, each line of CODE ends with a period.


### R Code

```
# PCCF+ GUIDE
# PART B: Adding your dataset and census data 

# Instruction: 
# - Replace the data file paths below with the respective file paths on your computer.

# STEP 1: Importing Datasets
# Note: Change all backslashes to forward slashes

# Import your dataset
mydataset <- read.csv("H:/PCCF Guide/Data/My_dataset.csv")

# Import data from part A - your postal codes combined with the PCCF+ file
mypostalcodespccfp <- read.csv("H:/PCCF Guide/Data/mypostalcodespccfp.csv")

# Import the census data file
census <- read.csv("H:/PCCF Guide/Data/census2016.csv")

# STEP 2: Combine the datasets mydataset and mypostalcodespccfp

# Rename the postal code variables in mydataset and mypostalcodespccfp pcode
names(mydataset)[names(mydataset)=="Postal.Code"] <- "pcode"
names(mypostalcodespccfp)[names(mypostalcodespccfp)=="PCODE"] <- "pcode"

# Remove the single space in pcode in mydataset
mydataset$pcode <- gsub(" ", "", mydataset$pcode) 

# Merge: combine the two datasets by matching the pcode variable

mydatasetpccfp <- merge(mydataset, mypostalcodespccfp, by="pcode")

# STEP 3: Combine the datasets mydatasetpccfp and census

# Rename the DA variables to dauid in mydatasetpccfp and census
names(mydatasetpccfp)[names(mydatasetpccfp)=="DAuid"] <- "dauid"
names(census)[names(census)=="COL0"] <- "dauid"

# Merge: combine the two datasets by matching the dauid variable
mydataset2 <- merge(mydatasetpccfp, census, by="dauid", all.x=TRUE)

# STEP 4: Export mydataset2

# Export mydataset2 to CSV in your output folder
write.csv(mydataset2,"H:/PCCF Guide/Data/My_dataset2.csv", row.names=FALSE)
```

### Stata Code

```
* PCCF+ Guide
* PART B: Adding your dataset and census data

>* Instruction:
*           - Replace the data file paths below with the respective file paths on your computer.

* STEP 1: Adding your dataset

* Import your dataset
insheet using "H:\PCCF Guide\Data\My_dataset.csv", clear
* Rename the postal code variable in your dataset pcode 
rename postalcode pcode
* Remove the space in pcode
replace pcode = subinstr(pcode, " ", "", .)
* Sort by pcode
sort pcode
* Save
save "H:\PCCF Guide\Data\mydataset.dta", replace

* Import the mypostalcodespccfp data file
* Note: The following import line of code is typed over a few lines
insheet coder version id pcode pr dauid db db_ir2016 csduid csdname csdtyp ///
          cma cmatype cmaname ctname tracted saccode sactype ccsuid feduid fedname ///
          dpluid dpltype dplname eruid ername caruid carname popctrrapuid ///
          popctrraname popctrratype popctrraclass csize csizemiz hruid hrename ///
          hrfname ahruid ahrename ahrfname sli rep_pt_type rpf pctype dmt h_dmt ///
          dmtdiff po qi source lat lon link_source link ncd ncsd prec comm_name ///
          airlift instflag resflag inuitlands btippe atippe qabtippe qnbtippe ///
          dabtippe dnbtippe qaatippe qnatippe daatippe dnatippe impflg da11uid ///
          db11uid da06uid da01uid ea96uid ea91uid         ea86uid  ea81uid ///
          using "H:\PCCF Guide\Data\mypostalcodespccfp.csv", clear

* Sort by pcode
sort pcode
* Save
save "H:\PCCF Guide\Data\mypostalcodespccfp.dta", replace

* Merge: Combine the Stata datasets mydataset and mypostalcodespccfp
use "H:\PCCF Guide\Data\mydataset.dta", clear
merge 1:1 pcode using "H:\PCCF Guide\Data\mypostalcodespccfp.dta"
drop _merge
save "H:\PCCF Guide\Data\mydatasetpccfp.dta", replace

* STEP 2: Adding census data

>* Import the mydatasetpccfp data file
use "H:\PCCF Guide\Data\mydatasetpccfp.dta", clear
* Sort by dauid
sort dauid
* Save
save "H:\PCCF Guide\Data\mydatasetpccfp.dta", replace

* Import the census data file
insheet using "H:\PCCF Guide\Data\census2016.csv", clear
* Rename the variable col0 dauid
rename col0 dauid
* Sort by dauid
sort dauid
* Save
save "H:\PCCF Guide\Data\census2016.dta", replace

* Merge: Combine the datasets mydatasetpccfp and census and only keep your DAs
use "H:\PCCF Guide\Data\mydatasetpccfp.dta", clear
merge 1:1 dauid using "H:\PCCF Guide\Data\census2016.dta"
keep if _merge==1|_merge==3
drop _merge
save "H:\PCCF Guide\Data\mydataset2.dta", replace

* STEP 3: Export mydatset2

* Export mydataset2 to CSV in your output folder
outsheet using "H:\PCCF Guide\Data\My_dataset2.csv", comma replace
```


### SPSS Code

```
* Encoding: UTF-8.
* PCCF+ GUIDE.
* PART B: ADDING YOUR DATASET AND CENSUS DATA. 

* Instructions: 
     - Replace the data file paths below with the respective file paths on your computer
     - Run the code below in chunks. The chunks of code are separated by at least one line of space. 

>* STEP 1: Adding your dataset.

* IMPORT My_dataset.csv, PREPARE it for merging & SAVE it as My_dataset.sav.
GET DATA /TYPE=TXT /FILE='H:\PCCF Guide\Data\My_dataset.csv'
/ENCODING=LOCALE
/DELCASE = LINE
/DELIMITERS = ","
/ARRANGEMENT = DELIMITED
/FIRSTCASE = 2
/VARIABLES= PostalCode A Age A.
COMPUTE PostalCode = replace(PostalCode, " ", "").
SORT CASES BY PostalCode (A).
SAVE OUTFILE='H:\PCCF Guide\Data\My_dataset.sav'
  /RENAME=(PostalCode = PCODE).
EXECUTE.

* IMPORT mypostalcodespccfp.csv, PREPARE it for merging & SAVE it as mypostalcodespccfp.sav.
GET DATA /TYPE=TXT /FILE='H:\PCCF Guide\Data\mypostalcodespccfp.csv'
/ENCODING=LOCALE
/DELCASE = LINE
/DELIMITERS = ","
/ARRANGEMENT = DELIMITED
/FIRSTCASE = 2
/VARIABLES= CODER A VERSION A ID A PCODE A PR A DAuid F8.0 DB A
DB_ir2016 A CSDuid A CSDname A CSDtyp A CMA A CMAtype A CMAname A CTname A Tracted A SACcode A SACtype A
CCSuid A FEDuid A FEDname A DPLuid A DPLtype A DPLname A ERuid A ERname A CARuid A CARname A PopCtrRAPuid A 
PopCtrRAname A PopCtrRAtype A PopCtrRAclass A CSize A CSizeMIZ A HRuid A HRename A HRfname A AHRuid A AHRename A
AHRfname A SLI A Rep_Pt_type A RPF A PCtype A DMT A H_DMT A DMTDIFF A PO A QI A Source A Lat A Long A Link_Source A
Link A nCD A nCSD A PREC A Comm_Name A AirLift A InstFlag A Resflag A InuitLands A BTIPPE A ATIPPE A QABTIPPE A
QNBTIPPE A DABTIPPE A DNBTIPPE A QAATIPPE A QNATIPPE A DAATIPPE A DNATIPPE A IMPFLG A DA11uid A DB11uid A DA06uid A DA01uid A EA96uid A EA91uid A EA86uid A EA81uid A.
SORT CASES BY PCODE (A).
SAVE OUTFILE='H:\PCCF Guide\Data\mypostalcodespccfp.sav'.
EXECUTE.

*MERGE My_dataset.sav and mypostalcodespccfp.sav & SAVE it as mydatasetpccfp.sav.
MATCH FILES
/FILE='H:\PCCF Guide\Data\My_dataset.sav'
/FILE='H:\PCCF Guide\Data\mypostalcodespccfp.sav'
/BY PCODE.
SORT CASES BY DAuid (A).
ALTER TYPE DAuid (A8).
>EXECUTE.
SAVE OUTFILE='H:\PCCF Guide\Data\mydatasetpccfp.sav'.
EXECUTE. 

* STEP 2: Adding census data.

* IMPORT census2016.csv, PREPARE it for merging & SAVE it as census2016.sav.
>GET DATA /TYPE=TXT /FILE='H:\PCCF Guide\Data\census2016.csv'
/ENCODING=LOCALE
/DELCASE = LINE
/DELIMITERS = ","
/ARRANGEMENT = DELIMITED
/FIRSTCASE = 2
/VARIABLES= COL0 A COL1 A COL2 A COL3 A COL4 A COL5 A COL6 A COL7 A COL8 A COL9 A.
COMPUTE COL0 = replace(COL0, '"', "").
EXECUTE.
SORT CASES BY COL0 (A).
ALTER TYPE COL0 (A8).
EXECUTE.
SAVE OUTFILE='H:\PCCF Guide\Data\census2016.sav'   /RENAME=(COL0 = DAuid).
EXECUTE.

>*MERGE mydatasetpccfp.sav and census2016.sav & SAVE it as mydataset2.sav.
MATCH FILES 
/FILE='H:\PCCF Guide\Data\mydatasetpccfp.sav' /IN=mypostalcodes
/FILE='H:\PCCF Guide\Data\census2016.sav'
/BY DAuid. 
SELECT IF mypostalcodes.
EXECUTE.
DELETE VARIABLES mypostalcodes.
EXECUTE.
SAVE OUTFILE='H:\PCCF Guide\Data\mydataset2.sav'.
EXECUTE.

* STEP 3: Export mydatset2.sav to CSV to your output folder.

SAVE TRANSLATE OUTFILE='H:\PCCF Guide\Data\My_dataset2.csv' /TYPE=CSV /MAP /REPLACE /FIELDNAMES /CELLS=LABELS.
EXECUTE. 
```

### Python Code

```
# PCCF+ GUIDE
# PART B: Adding your dataset and census data 

# Instruction: 
#- Replace the data file paths below with the respective file paths on your computer.

# STEP 1: Importing Datasets
# Note: Change all backslashes to forward slashes

# Import necessary Python library
import pandas as pd

# Import your dataset
>mydataset = pd.read_csv("H:/PCCF Guide/Data/My_dataset.csv")

# Import data from part A - your postal codes combined with the PCCF+ file
mypostalcodespccfp = pd.read_csv("H:/PCCF Guide/Data/mypostalcodespccfp.csv", encoding="latin-1")

# Import the census data file
census = pd.read_csv("H:/PCCF Guide/Data/census2016.csv", encoding="latin-1")

# STEP 2: Combine the datasets mydataset and mypostalcodespccfp

# Rename the postal code variables in mydataset and mypostalcodespccfp pcode
mydataset = mydataset.rename({'Postal Code':'pcode'}, axis=1)
mypostalcodespccfp = mypostalcodespccfp.rename({'PCODE':'pcode'}, axis=1)

# Remove the single space in pcode in mydataset
# Note: Ignore the warning
import warnings
warnings.filterwarnings("ignore")
for index in range(0,len(mydataset)):
  mydataset["pcode"][index] = mydataset["pcode"][index].replace(" ", "")
warnings.resetwarnings()

# Merge: combine the two datasets by matching the pcode variable
mydatasetpccfp = mydataset.merge(mypostalcodespccfp, how="right", on="pcode")

# STEP 3: Combine the datasets mydatasetpccfp and census

# Rename the DA variables to dauid in mydatasetpccfp and census
mydatasetpccfp = mydatasetpccfp.rename({'DAuid':'dauid'}, axis=1)
census = census.rename({'COL0':'dauid'}, axis=1)

# Merge: combine the two datasets by matching the dauid variable
mydataset2 = mydatasetpccfp.merge(census, how="left", on="dauid")

# STEP 4: Export mydatset2

# Export mydataset2 to CSV in your output folder
mydataset2.to_csv("H:/PCCF Guide/Data/My_dataset2.csv", index=False)
```

**Technique:** [Quantitative Data Analysis](https://mdlutoronto.github.io/tutorials-search/?technique=Quantitative+Data+Analysis) \| Tools: [R](https://mdlutoronto.github.io/tutorials-search/?tool=R), [SAS](https://mdlutoronto.github.io/tutorials-search/?tool=SAS), [SPSS](https://mdlutoronto.github.io/tutorials-search/?tool=SPSS) \| Data Format: [Microdata](https://mdlutoronto.github.io/tutorials-search/?dataFormat=Microdata)

**Date Created:** 2023\-06\-06 **Updated:** 2023\-07\-13