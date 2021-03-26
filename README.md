V2 update :  Version 2 of the post_accubook tool replaces 2 QR codes with a single QR code and adds some automation to the pre-screening process. Users need to open a new patient record in Pinnacle then ALT-TAB into a PowerShell Prompt, then scan the QR code.  This will auto complete all neccessary fields for Pinnacle Pre-Screening upto the PDS matching Patient confirmation section.
*Barcode Scanners need to be configured to add the RETURN character at the end.

# Accubook_tools

A set of tools to help with
1. Booking patients for their vaccination (from a TPP clinical system)
2. Produce a printable QR code sheet to help pinnacle data entry

credits to 
SG@MLS and R.Pacifico based on the original work by [DrMikeyS](https://github.com/DrMikeyS/COVIDVaccinePatientSlips).


# Instructions

download the and extract the files and folders from the zip file:  
there should be 2 folders; 'Pre Accubook' with an empty csv file and a PowerShell script and 'Post Accubook' with an html file QR tool.

1. Pre-Accubook : SystemOne searches ready for Accubook

create searches in S1 -> run search -> right click, ->breakdown results -> expand demographics tree -> select Title (then press refresh)
-> select firstname (refresh) -> select surname (refresh) -> Date of birth (refresh) -> nhs number (refresh) -> telecom number (refresh) 
-> export csv -> remove entire colomn G  'Patient count' -> save as ... 
-> navigate to the folder where you have the 'S1_to_Accubook.ps1' script
-> save file into the folder overwriting the existing csv file called accu-input.csv 
-> right click the ps1 script file -> select 'Run with Powershell' 
-> accept any security prompt then wait -> once completed you will now see a file called accu-output.csv ready to upload to accubook 
-> please remember to remove the 'accu-output.csv' file from the folder once it is uploaded to Accubook (do not delete the accu-input.csv though)


2. Post-Accubook  -> generate QR codes for Pinnacle:

go to accubook -> surgery name -> booked list -> click export on the relevant clinic -> save file to PC 
-> right click on the downloaded QR tool and select 'open with' then chose Chrome 
-> press the 'Choose file' button and navigate and select the downloaded csv file from Accubook 
-> this will generate the QR codes -> set printer to landscape -> print


# IG and Security

No data is transferred anywhere when using this tool, all the process is done in your web browser. The tool uses some open source libraries to work. Using the tool is entirely at your own risk.
