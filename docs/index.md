---
title: "PCCF+ Guide"
layout: "home"
description: "In this tutorial, we will use the Postal Code Conversion File Plus (PCCF+) to match postal codes to dissemination areas in order to incorporate additional neighbourhood-level demographic data into your dataset."
permalink: "/"  #! Remove this if not the homepage
staff:
 - name: Nick Field
   link: https://library.utoronto.ca/staff/nick-field
maintainer:
 - name: Nadia Muhe
   link: https://library.utoronto.ca/staff/nadia-muhe
 - name: Leanne Trimble
   link: https://library.utoronto.ca/staff/leanne-trimble
nav_order: 0
has_children: true
---

# PCCF+ Guide

In this tutorial, we will use the Postal Code Conversion File Plus (PCCF\+) to match postal codes to dissemination areas in order to incorporate additional neighbourhood\-level demographic data into your dataset.

There are multiple postal code products that can accomplish this task. For an overview, see our general PCCF page [https://mdl.library.utoronto.ca/collections/numeric\-data/census\-canada/postal\-code\-conversion\-file](https://mdl.library.utoronto.ca/collections/numeric-data/census-canada/postal-code-conversion-file). In this tutorial, we will use the PCCF\+ file, which uses a population\-weighted random allocation to assign a postal code to a geographic area. This is an alternative method to using the standard PCCF file which uses a Single Link Indicator (SLI) to assign a postal code to the geographic area with the majority of dwellings. The PCCF\+ tends to work better when your postal codes are rural or when the “vintage” of your postal codes pans more than one census. See [this guide](https://cudo.carleton.ca/system/files/dli_training/3859/accoleds2015-pccfpccfplus-handout.pdf) Statistics Canada created for more information on selecting a PCCF product that meets your needs.

The following guide contains two parts and an appendix. In part A, you will start with the postal codes from your dataset and use the PCCF\+ to assign Statistics Canada standard geographic identifiers to your postal codes. In part B, you will enrich your final dataset from part A with your dataset and census data. Because the PCCF\+ file is a SAS file, part A must be completed using SAS. This guide shows you how to complete part B using SAS as well, and the appendix contains additional code to run part B using R, Stata, SPSS or Python code.

<!-- **TABLE OF CONTENTS**  
[Part A](#part-a-use-the-pccf-to-assign-standard-geographic-codesnames-to-your-postal-codes): Use the PCCF\+ to assign standard geographic codes/names to your postal codes  
[Part B](#part-b-adding-your-dataset-and-census-data): Adding your dataset and census data

**[APPENDIX](#appendix)**  
[R Code](#r-code)  
[Stata Code](#stata-code)  
[SPSS Code](#spss-code)  
[Python Code](#python-code) -->




**Technique:** [Quantitative Data Analysis](https://mdlutoronto.github.io/tutorials-search/?technique=Quantitative+Data+Analysis) \| Tools: [R](https://mdlutoronto.github.io/tutorials-search/?tool=R), [SAS](https://mdlutoronto.github.io/tutorials-search/?tool=SAS), [SPSS](https://mdlutoronto.github.io/tutorials-search/?tool=SPSS) \| Data Format: [Microdata](https://mdlutoronto.github.io/tutorials-search/?dataFormat=Microdata)

**Date Created:** 2023\-06\-06 **Updated:** 2023\-07\-13
