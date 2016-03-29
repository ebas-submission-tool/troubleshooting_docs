Troubleshooting file submission errors
============

> ### Note that the lines giving you errors may vary due to the dynamic nature of the metadata fields. Please browse through the error messages and see if they are similar to yours, if they are you could try the proposed solution. If you have any fixes you would like to submit, you could fork the github repository <https://github.com/richard-olav/troubleshooting-ebas-submit-errors.git> or send an e-mail to <ror@nilu.no>.

***
ERROR: **line 3**

Instrument type: **nephelometer** 

	Organization code syntax error, should be XX99Y

**Possible solution:**
Make sure you have the correct number of charachters, e.g. NO01L	

***

ERROR: **line 33**

Instrument type: **nephelometer**

	Revision date (xxxxxxxxxx), must be the same day as RDATE specified in line 7
	
**Possible solution:**
Make sure revision date on this line matches the revision date on line 7

***

ERROR: **line 12**

Instrument type: **nephelometer**

> **Note:** This is an example of an error were one of the flag columns is wrong. A VMISS error could be for any other of the flag columns aswell 

	VMISS[11]: illegal missing value for flag column: '0.999'. Should be 9.[999]... (groups of 3 digiits). Flag skipped

**Possible solution:**
Flag column number 12 is incorrect, flag column is set to 0.999 but should be 9.999 

***

ERROR: **line 14-23**

Instrument type: **nephelometer**

	illegal metadata element X for instrument Y and component Z

**Possible solution:**
Check that the instrument type is correct. The instrument type is case sensitive, and a common error is using capital letters for the instrument type

***

ERROR: **line 37**

Instrument type: **sun_tracking_filter_radiometer**

        NLHEAD and NNCOM are inconsisten 

**Possible solution:**
NLHEAD is total number of lines in the header, see line 1 in your file. NNCOM is the number of normal comment lines (this line is found after the "Number of special comment lines", which usually is 0).
This is all the following header lines contain information for classifying the dataset in the database. 
Most likely you are getting this error because the number of header lines defined in your nasa-ames file does not add up. 
You should check that there is not any inconsistencies 
  
***

ERROR: **line 71**

Instrument type: **sun_tracking_filter_radiometer

> **Note** The line you will be getting this error on may vary, due to the dynamic nature of the metadata fields.

	Originator: <surname>, <firstname> not found in ONAME (line 2)        

**Possible solution:**
Make sure the data originator is the same in this line as in line 2.

***

ERROR: ** **
Instrument type: ** **

        Error Message

**Possible solution:**

***

ERROR: ** **
Instrument type: ** **

	Error Message

**Possible solution:**

***
