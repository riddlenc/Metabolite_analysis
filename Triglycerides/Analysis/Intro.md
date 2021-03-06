# Processing 96 well plate data

Often, biological samples are processed in a 96 well plate format.  Output from these assays is typically stored in tab delineated files, .csv files, .xlsx files or similar, often containing meta data in addition to the raw data.  Thus, these raw files need to be processed, both for quality control and to extract the data for further processing. 

## 1. Spectrophotometer data - triglyceride assay
In the Riddle lab, one type of 96 well plate data generated derives from triglyceride assays that generate two output files per assay, an initial absorbance measure (IA) and a final absorbance measure (FA).  As we will have over 100 plates to process, we wanted a way to automatically carry out the QC and the reformatting of the data. Two R bash scripts were written to accomplish these goals.

This script requires the samples to be loaded into the 96 well plate in the layout shown 
[here.](https://github.com/riddlenc/Metabolite_analysis/blob/cb474b9fa45fbb17ac460949b0b49df65185fca2/Triglycerides/Layout.xlsx)  An example of the spectrophotometer output file format can be found [here.](https://github.com/riddlenc/Metabolite_analysis/blob/042dc83e2708f3e1b93ea726faaf59317afcfe0c/Triglycerides/test.xlsx)

*a) Standard curve and QC script*
This R script generates a standard curve and carries out some QC assessments.  The script can be found 
[here.](https://github.com/riddlenc/Metabolite_analysis/blob/78071930e5bbd384c367918d01ff35ad3e0203b5/Triglycerides/Analysis/Triglycerides_standard_curve_v3.R)
NOTE: This R scripts plots the raw OD readings without blank subtraction. 

*b) Data reformatting script*
This R script extracts the raw data from the IA and FA data files, reformats the data, calculates glycerol and triglyceride concentration for each sample and appends it to a master data file.  The script can be found 
[here.](https://github.com/riddlenc/Metabolite_analysis/blob/78071930e5bbd384c367918d01ff35ad3e0203b5/Triglycerides/Analysis/Analysis_script.R)


![#f03c15](https://via.placeholder.com/15/f03c15/000000?text=+) `NOTE: Make sure to adjust the script - or edit your data file - if you have diluted your fly samples prior to running the assay.`
