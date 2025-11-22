# GetCDISCCodelist
## SAS Macro for Fetching CDISC Controlled Terminology (CT) Codelists
This SAS macro retrieves and filters CDISC Controlled Terminology (CT) codelists for various CDISC standards (SDTM, ADaM, CDASH, etc.). The macro interacts with the CDISC Terminology API to fetch the latest terminology version and filters the codelists based on the specified input parameters.

### This repository is an adapted version of Saikrishnareddy Yengannagari’s original package (https://github.com/kusy2009/getCDISCCOdelist) tailored for the SAS Package Framework, and the original license remains the property of Saikrishnareddy Yengannagari.　　

<img width="360" height="360" alt="GetCDISCCodelist_small" src="https://github.com/user-attachments/assets/38a5f3ed-49e1-47b8-bdb1-bf4a1243b0f4" />  

## Features
  - Dynamic Version Fetching: Automatically fetches the latest version of Controlled Terminology (CT) if not specified.
  - Multiple Standards Support: Supports multiple CDISC standards including SDTM, ADaM, CDASH, DEFINE-XML, SEND, and others.
  - Flexible Filtering: Allows filtering by codelist ID or CodelistCode.
  - Extensible Data: Flags if the codelist is extensible (i.e., if it supports additional terms beyond the official list).
  - Error Handling: Provides detailed error messages if the provided codelist or standard is invalid.

## Prerequisites
Before you can use this macro, make sure you have the following:
  - CDISC API Access: You will need an API Key for the CDISC API. If you don’t have one, you can obtain it from CDISC's website.

## Syntax
~~~sas
%macro GetCDISCCodelist(
    codelistValue=,  /* The codelist name (e.g., AGEU, PARAMCD) */
    codelistType=ID,  /* Match by ID or CodelistCode */
    standard=SDTM,  /* Default to SDTM */
    version=%str(), /* Version of Controlled Terminology (empty to pull latest) */
    outlib=WORK,/* Output Library */
    cdiscapikey=  /*CDISC API key*/
);
~~~

## Parameters
### codelistValue
  - Required: Yes
  - Type: Character
  - Description: The name of the codelist (e.g., AGEU, PARAMCD, DTYPE).
### codelistType
  - Required: No
  - Type: Character (ID or CodelistCode)
  - Default: ID
  - Description: Specify whether to filter by ID or CodelistCode. By default, the macro will filter by ID.
### standard
  - Required: No
  - Type: Character
  - Default: SDTM
  - Description: The CDISC standard for which to retrieve the codelist. Valid values include:
     - SDTM (default)
    - ADAM
    - CDASH
    - DEFINE-XML
    - SEND
    - DDF
    - GLOSSARY
    - MRCT
    - PROTOCOL
    - QRS
    - QS-FT
    - TMF
### outlib
  - Required: No
  - Type: Library
  - Default: WORK
  - Description: The SAS library where the resulting datasets will be saved.
### cdiscapikey
  - Required: Yes
  - Description: The SAS library where the resulting datasets will be saved.
  - CDISC API key
  - 
## Output
The macro generates the following outputs:  
  - Merged Codelist Dataset: A dataset containing the codelist values and their associated terms.
  - Extensibility Flag: If the codelist is extensible, the output dataset will include a flag indicating so.
  - Filtered Codelists: The codelist is filtered based on the provided codelistValue and codelistType parameters.

## Example_Usage
~~~sas
%GetCDISCCodelist(codelistValue=ACN,cdiscapikey= xxxxx);
~~~
<img width="484" height="232" alt="image" src="https://github.com/user-attachments/assets/c57e4acd-28ac-43b6-87f5-0d1d689a1160" />  

<img width="778" height="446" alt="image" src="https://github.com/user-attachments/assets/8da62dda-f050-45c5-8fbc-14d9a2f7a08d" />




## Conclusion
This macro can be a very useful tool for fetching and working with CDISC Controlled Terminology (CT) codelists in your clinical trial datasets. If you have any questions or suggestions, feel free to reach out or create an issue in the GitHub repository.
