---
UID: NS:winsplp.BranchOfficeJobDataError
title: BranchOfficeJobDataError
author: windows-driver-content
description: This structure contains the necessary data for logging a branch office job failure event on a remote server. This is based on standard job-related data available to the spooler.
old-location: print\branchofficejobdataerror.htm
old-project: print
ms.assetid: 947C508E-2EB9-451D-AA8D-DCDDE27DEBE6
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: BranchOfficeJobDataError structure [Print Devices], print.branchofficejobdataerror, winsplp/PBranchOfficeJobDataError, PBranchOfficeJobDataError structure pointer [Print Devices], winsplp/BranchOfficeJobDataError, PBranchOfficeJobDataError, BranchOfficeJobDataError, *PBranchOfficeJobDataError
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Winsplp.h
apiname:
-	BranchOfficeJobDataError
product: Windows
targetos: Windows
req.typenames: "*PBranchOfficeJobDataError, BranchOfficeJobDataError"
req.product: Windows 10 or later.
---

# BranchOfficeJobDataError structure


## -description


This structure contains the necessary data for logging a branch office job failure event on a remote server. This is based on standard job-related data available to the spooler.


## -syntax


````
typedef struct {
  DWORD    LastError;
  LPWSTR   pDocumentName;
  LPWSTR   pUserName;
  LPWSTR   pPrinterName;
  LPWSTR   pDataType;
  LONGLONG TotalSize;
  LONGLONG PrintedSize;
  DWORD    TotalPages;
  DWORD    PrintedPages;
  LPWSTR   pMachineName;
  LPWSTR   pJobError;
  LPWSTR   pErrorDescription;
} BranchOfficeJobDataError, *PBranchOfficeJobDataError;
````


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

