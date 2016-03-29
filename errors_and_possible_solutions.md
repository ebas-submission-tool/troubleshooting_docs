Troubleshooting file submission errors
============

***
**ERROR:** line 3
**Instrument type:** nephelometer 

	Organization code syntax error, should be XX99Y

**Possible solutions:**
Make sure you have the correct number of charachters, e.g. NO01L	

***

**ERROR:** line 33
**Instrument type:** nephelometer

	Revision date (xxxxxxxxxx), must be the same day as RDATE specified in line 7
	
**Possible solutions**
Make sure revision date on this line matches the revision date on line 7

***

**ERROR** line 12
**Instrument type:** nephelometer

> **Note:** This is an example of an error were one of the flag columns is wrong. A VMISS error could be for any other of the flag columns aswell 

	VMISS[11]: illegal missing value for flag column: '0.999'. Should be 9.[999]... (groups of 3 digiits). Flag skipped

**Possible solutions**
Flag column number 12 is incorrect, flag column is set to 0.999 but should be 9.999 

***

**Error** line 14-23
**Instrument type:** nephelometer

	illegal metadata element X for instrument Y and component Z

**Possible solutions**
Check that the instrument type is correct. The instrument type is case sensitive, and a common error is using capital letters for the instrument type

***
