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
