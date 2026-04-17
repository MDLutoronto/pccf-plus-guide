---
title: Part A. Use the PCCF + to assign standard geographic codes/names to your postal codes
parent: PCCF+ Guide
nav_order: 1
layout: default
---

Part A: Use the PCCF\+ to assign standard geographic codes/names to your postal codes
-------------------------------------------------------------------------------------

In this section, you will prepare your postal codes and assign geographic data to them using the PCCF\+.

1. First, you need to download the PCCF\+ dataset from the MDL website: [https://mdl.library.utoronto.ca/collections/numeric\-data/census\-canada/postal\-code\-conversion\-file](https://mdl.library.utoronto.ca/collections/numeric-data/census-canada/postal-code-conversion-file).

    Choose the census year of interest:

    <img src='{{ '/assets/images/PCCFPlus_A_001.png' | relative_url }}' alt='A screenshot of the Map and Data Library website. The title on the page reads: Postal code conversion file. Under the title the page reads: To download PCCF data, select the census year you are interested in, followed by a list of years. There is an arrow pointing to the year 2016. ' title='' width='100%' height='773' />

    Scroll through the list and find the latest update of PCCF\+ file. Click on Access data to download the dataset.

    <img src='{{ '/assets/images/PCCFPlus_A_002a.png' | relative_url }}' alt='Under a section titled: November 2020 postal codes, there are three sections: PCCF original edition (released Dec 2020); PCCF+ (released Feb 2021); PCFRF (Federal Ridings File) (released Dec 2020). Under the PCCF+ section, an arrow points to a hyperlink titled: Access data (restricted) ' title='' width='70%' height='782' />

    Please carefully read through the end\-user license agreement.

    <img src='{{ '/assets/images/PCCFPlus_A_003.png' | relative_url }}' alt='University of Toronto Library End-Use License Agreement for Postal Code(OM) Conversion Files' title='' width='100%' height='704' />

    At the bottom of the page, click the link to authenticate with your UTORid. The download will then start automatically.

    <img src='{{ '/assets/images/PCCFPlus_A_004.png' | relative_url }}' alt='The end of the End-Use License Agreement. At the bottom there is a line that reads: To access Postal Code Data log in with your UTORid via University of Toronto Web Login. There is an arrow pointing to the part that says log in with your UTORid via University of Toronto Web Login, which is a hyperlink. ' title='' width='100%' height='864' />

    If you wish, move the file from your Downloads folder to some location where you will find it again later.

    The download is a compressed file which must be uncompressed (or “unzipped”). Right\-click on the file and choose Extract All. On a Mac you can simply double\-click on the file.

    <img src='{{ '/assets/images/PCCFPlus_A_005.png' | relative_url }}' alt='A zip-file titled PCCF7D in file explorer. The file is highlighted, and there is a drop-down menu. The option 7-Zip is selected, followed by Extract to "PCCF7D\"' title='' width='90%' height='603' />

 

2. To assign geographic data to your postal codes using the PCCF\+, you can use the following comprehensive [Statistics Canada PCCF\+ guide](https://mdl.library.utoronto.ca/sites/default/public/mdldata/open/canada/national/statcan/postalcodes/pccfplus/2016/pccf_plus_7D/SettingupPCCFp_ENG.pptx). It explains in detail how to set up and run the PCCF\+ with your own postal codes so we will not repeat the work here. The steps in the guide include:

    1. Creating an input file from your postal codes’ dataset. Be mindful of column names in this step.
    2. Running PCCF\+. This step includes using the PCCF\+ dataset and code downloaded from the Map & Data library general PCCF webpage and modifying six lines of SAS code.
    3. Checking outputs. In this final step, you want to check the output data file to see if it has been populated and the problem files to flag any problematic postal codes.

We complete the steps in this guide using the postal codes from [My\_dataset.csv](https://maps.library.utoronto.ca/workshops/PCCF/My_dataset.csv). Our input file is [My\_postalcodes.csv](https://maps.library.utoronto.ca/workshops/PCCF/My_postalcodes.csv). And in the last step, we save our output dataset as [mypostalcodespccfp.csv](https://maps.library.utoronto.ca/workshops/PCCF/mypostalcodespccfp.csv)

**Technique:** [Quantitative Data Analysis](https://mdlutoronto.github.io/tutorials-search/?technique=Quantitative+Data+Analysis) \| Tools: [R](https://mdlutoronto.github.io/tutorials-search/?tool=R), [SAS](https://mdlutoronto.github.io/tutorials-search/?tool=SAS), [SPSS](https://mdlutoronto.github.io/tutorials-search/?tool=SPSS) \| Data Format: [Microdata](https://mdlutoronto.github.io/tutorials-search/?dataFormat=Microdata)

**Date Created:** 2023\-06\-06 **Updated:** 2023\-07\-13
