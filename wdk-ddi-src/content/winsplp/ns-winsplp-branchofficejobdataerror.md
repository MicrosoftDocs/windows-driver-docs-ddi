---
UID: NS:winsplp.__unnamed_struct_1
title: BranchOfficeJobDataError (winsplp.h)
description: This structure contains the necessary data for logging a branch office job failure event on a remote server. This is based on standard job-related data available to the spooler.
old-location: print\branchofficejobdataerror.htm
tech.root: print
ms.assetid: 947C508E-2EB9-451D-AA8D-DCDDE27DEBE6
ms.date: 04/20/2018
keywords: ["BranchOfficeJobDataError structure"]
ms.keywords: "*PBranchOfficeJobDataError, BranchOfficeJobDataError, BranchOfficeJobDataError structure [Print Devices], PBranchOfficeJobDataError, PBranchOfficeJobDataError structure pointer [Print Devices], print.branchofficejobdataerror, winsplp/BranchOfficeJobDataError, winsplp/PBranchOfficeJobDataError"
f1_keywords:
 - "winsplp/BranchOfficeJobDataError"
 - "BranchOfficeJobDataError"
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Winsplp.h
api_name:
- BranchOfficeJobDataError
product:
- Windows
targetos: Windows
req.typenames: BranchOfficeJobDataError, *PBranchOfficeJobDataError
---

# BranchOfficeJobDataError structure


## -description


This structure contains the necessary data for logging a branch office job failure event on a remote server. This is based on standard job-related data available to the spooler.


## -struct-fields




### -field LastError

Specifies the LastError at the time the event was logged.


### -field pDocumentName

Specifies the name of the printed document.


### -field pUserName

Specifies the user who submitted the job.


### -field pPrinterName

Specifies the name of the print connection.


### -field pDataType

Specifies the data type of the job.


### -field TotalSize

Specifies the 64-bit size of the job.


### -field PrintedSize

Specifies the 64-bit size of the job.


### -field TotalPages

Specifies the total number of pages in the job.


### -field PrintedPages

Specifies the number of pages currently printed.


### -field pMachineName

Specifies the name of the client machine printing the job.


### -field pJobError

Specifies the failure code for a JOB_ERROR event.


### -field pErrorDescription

Specifies the text description of the error, if available.

