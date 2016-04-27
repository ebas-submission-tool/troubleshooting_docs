Troubleshooting file submission errors
============

> ### Note that the lines giving you errors may vary due to the dynamic nature of the metadata fields. Please browse through the error messages and see if they are similar to yours, if they are you could try the proposed solution. If you have any fixes you would like to submit, you could fork the github repository <https://github.com/richard-olav/troubleshooting-ebas-submit-errors.git> or send an e-mail to <ror@nilu.no>.

## Instrument type: **nephelometer**

***

	Organization code syntax error, should be XX99Y

**Possible solution:**
Make sure you have the correct number of charachters, e.g. NO01L	

***

	Revision date (xxxxxxxxxx), must be the same day as RDATE specified in line 7
	
**Possible solution:**
Make sure revision date on this line matches the revision date on line 7

***

> **Note:** This is an example of an error were one of the flag columns is wrong. A VMISS error could be for any other of the flag columns aswell 

	VMISS[11]: illegal missing value for flag column: '0.999'. Should be 9.[999]... (groups of 3 digiits). Flag skipped

**Possible solution:**
Flag column number 12 is incorrect, flag column is set to 0.999 but should be 9.999 

***

	illegal metadata element X for instrument Y and component Z

**Possible solution:**
Check that the instrument type is correct. The instrument type is case sensitive, and a common error is using capital letters for the instrument type

***

##Instrument type: sun_tracking_filter_radiometer

***

        NLHEAD and NNCOM are inconsisten 

**Possible solution:**
NLHEAD is total number of lines in the header, see line 1 in your file. NNCOM is the number of normal comment lines (this line is found after the "Number of special comment lines", which usually is 0).
This is all the following header lines contain information for classifying the dataset in the database. 
Most likely you are getting this error because the number of header lines defined in your nasa-ames file does not add up. 
You should check that there is not any inconsistencies 
  
***

> **Note** The line you will be getting this error on may vary, due to the dynamic nature of the metadata fields.

	Originator: <surname>, <firstname> not found in ONAME (line 2)        

**Possible solution:**
Make sure the data originator is the same in this line as in line 2.

***

##Instrument type: smps

***

        Organization syntax error, should be: code, name, acronym, unit, addr1, addr2, zip, city, country

**Possible solution:**
Check that the number of commas and order of input fields as as in the string above. Leave empty fields blank, but remember, you still need to provide the correct number of commas as in the string above.  

***

	Station other IDs: syntax error. Should be like 'Station-ID (Framework or project)[, ...]'

**Possible solution:**
If this field is blank, you can leave this line all together. If you do so, make sure you adjust the the total number of headerlines in line 1 and number of normal comment lines.

***

	Originator: syntax error: '<your input is listed here>'. 11 elements needed, should be 'Last name, First name, Email, Organization name, Organization acronym, Organization unit, Address line 1, Address line 2, ZIP code, City, Country'.

**Possible solution**
Often a comma is left out. Make sure that the number of elements are 11. If there are data fields left out, you still it blank between the commas.

***

	Regime/Matrix/Component combination 'IMG'/'PM10'/'particle_number_size_distribution' is not defined

**Possible solutions**
The matrix identifier is case sensitive. Therefore make sure that you use exactly the same syntax as in the documentation. Avoid e.g. PM10 with capital letters, instead use pm10. For correct syntax, see the following link <http://www.gaw-wdca.org/SubmitData/RegularAnnualDataReporting/regularformatcommentsauxheaderline12.aspx> 

***

Instrument type: tsmps

***
	
	Organization syntax error, should be: code, name, acronym, unit, addr1, addr2, zip, city, country

**Possible solutions**
When filling in details of the sponsoring organisation you must make sure that all fields are included, and that you have the right amount of commas. If there is an empty value, leave it blank between the commas, seperating the fields, in the right order. 

***

	Variable 143: value/flag inconsistent: value=9.99, flags=[999]; valid value and missing flag
	Variable 142: value/flag inconsistent: value=17.2, flags=[999]; valid value and missing flag
	Variable 138: value/flag inconsistent: value=89.8, flags=[999]; valid value and missing flag

	ERROR   : line 11: number of VSCAL elements (146) does not match NV (145)
	ERROR   : line 12: number of VMISS elements (146) does not match NV (145)
	ERROR   : line 158: NSCOML: syntax error
	ERROR   : line 2764: DATA[146]: value > VMISS is not allowed
	ERROR   : line 158: Last variabe must have a flag


	Also:ERROR: line 8852: DATA[11]: value does not match missing value definition (VMISS)


**Possible solutions**

***

##Instrument type: chemiluminescence_photometer

***
	number of VMISS elements (18) does not match NV (17)
	
**Possible solutions**

***

	unknown metadata element 'Zero/negative values'

**Possible solutions**
This error message was given because there was a blank space between the metadata element definition and colon. E.g. "Zero/negative values :", instead it should be "Zero/negative values:". Therefore make sure that you follow the exact same syntax as in the documentation. 

***

        number of VMISS elements (16) does not match NV (17)

**Possible solutions**
Maybe it is like, number of missing values are 16, and this does not match the number of variables, which are 17

***

        illegal metadata element Location for instrument chemiluminescence and component ozone

**Possible solutions**

***

##Instrument type: nephelometer

***

        Method ref: syntax error: 'FI0050L_neph_control_lev2_0_0_3'. Should be NN12T_AZaz09+.' (NN12T: Organization code (NN: nation code, 12: 2 digit organization number, T: organization type character), AZaz09+.: free text as method description (legal characters are A-Z, a-z, 0-9, -, _, +, .))

**Possible solutions**
Make sure that the Method reference contains the lab code, see line 3 and unique reference to lab internal SOP.

***

        unknown metadata element 'Zero/negative values'

**Possible solutions**

***

        data line does not contain x values
	value does not match missing value definition

**Possible solutions**


***


## Internal Server Error (500).

There could be multiple reasons why you are getting this error. 

* A reason why you are getting this error could be that you are using invalid characters. You can troubleshoot this by checking the charachter encoding. You can check the character encoding using firefox. Open firefox. Go to File-> Open File and then select your nasa-ames file. Then go to View -> Text Encoding and see what type of encoding you file is using. If you e.g. see that you are using "Western" encoding, switch to Unicode. If you have invalid charachters these will likely look something like this, e.g. -40�C instead of -40°C or H�rger instead of Hörger. The character encoding should be set to Unicode or UTF-8. 

* Mention session timeout in documentation.

