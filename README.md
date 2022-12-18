
# dl-aamva

  

AAMVA [specification](https://www.aamva.org/getmedia/99ac7057-0f4d-4461-b0a2-3a5532e1b35c/AAMVA-2020-DLID-Card-Design-Standard.pdf)

  
  

## Installation

  

```npm i dl-aamva```

or

```yarn add dl-aamva```

  

## Usage

  

**typescript**

  

```import AAMVA from "dl-aamva";```

  

**javascript**

  

```const AAMVA = require("dl-aamva");```

  

```
const rawDocument = `@
ANSI 636014090102DL00410294ZC03350024DLDAQY8146375
DCSGOMEZ
DDEN
DACISAIHA
DDFN
DADNONE
DDGN
DCAC
DCB01
DCDNONE
DBD04262019
DBB02081999
DBA02082024
DBC1
DAU069 IN
DAYBRO
DAG1839 NELSON BLVD APT 134
DAISELMA
DAJCA
DAK936620000
DCF04/03/201963313/08FD/24
DCGUSA
DAW155
DAZBLK
DCK19116Y81463750401
DDAF
DDB08292017
DDJ02082020
DDK1
ZCZCABRN
ZCBBLK
ZCC
ZCD`;

const document = AAMVA.raw(rawDocument);
console.log(document);

const base64RawDocument = 'QAoeDUFOU0kgNjM2MDMzMDkwMDAxREwwMDMxMDI3OURMREFRNTE5NDMxNwpEQ1NMVUtVVElOCkRERU4KREFDRE1JVFJZCkRERk4KREFETklLT0xBRVZJQ0gKRERHTgpEQ0FECkRDQk5PTkUKRENETk9ORQpEQkExMTEwMjAyNQpEQkQyMDI1LTA4LTE0CkRCQjA4MTQyMDAwCkRCQzEKREFZQkxLCkRBWkJBTApEQVUwNzAgaW4KREFHMTE2NDUgSkFWQSBTVApEQUlDWVBSRVNTCkRBSkFMCkRBSzIyMDEyODA5MSAgCkRDR1VTQQpEQ0ZWRDk5NTkxOEExNDM4SgpEQ0pZVDY2NjM3MlA5NzI3QQpEQ0tHWDE5MTgzN1M5ODQxRApEREFGCkREQjExMjcyMDE2DQ==';

const base64Document = AAMVA.base64(base64RawDocument);
console.log(base64Document);
```

***

**Output:**

```
{
	"header": {
		"separator": "\n",
		"terminator": "\r",
		"fileType": "ANSI",
		"iin": "636033",
		"version": 9,
		"jurisdictionVersion": 0,
		"numberOfEntries": 1
	},
	"subfiles": [{
		"type": "DL",
		"offset": 31,
		"length": 279,
		"data": [
			"DAQ5194317",
			"DCSLUKUTIN",
			"DDEN",
			"DACDMITRY",
			"DDFN",
			"DADNIKOLAEVICH",
			"DDGN",
			"DCAD",
			"DCBNONE",
			"DCDNONE",
			"DBA11102025",
			"DBD2025-08-14",
			"DBB08142000",
			"DBC1",
			"DAYBLK",
			"DAZBAL",
			"DAU070 in",
			"DAG11645 JAVA ST",
			"DAICYPRESS",
			"DAJAL",
			"DAK220128091 ",
			"DCGUSA",
			"DCFVD995918A1438J",
			"DCJYT666372P9727A",
			"DCKGX191837S9841D",
			"DDAF",
			"DDB11272016"
		]}
	],
	"data": {
		"idNumber": "5194317",
		"familyName": "LUKUTIN",
		"familyNameTruncation": "N",
		"firstName": "DMITRY",
		"firstNameTruncation": "N",
		"middleName": "NIKOLAEVICH",
		"middleNameTruncation": "N",
		"vehicleClass": "D",
		"restrictionCodes": "NONE",
		"endorsementCodes": "NONE",
		"expirationDate": "2025-11-10",
		"issueDate": "2025-08-14",
		"dateOfBirth": "2000-08-14",
		"sex": "M",
		"eyeColor": "BLK",
		"hairColor": "BAL",
		"height": "070 in",
		"address": "11645 JAVA ST",
		"city": "CYPRESS",
		"state": "AL",
		"zip": "220128091",
		"country": "USA",
		"discriminator": "VD995918A1438J",
		"auditInformation": "YT666372P9727A",
		"inventoryControlNumber": "GX191837S9841D",
		"complianceType": "F",
		"cardRevisionDate": "2016-11-27"
	}
}
```