---
UID: NS:winsplp.BranchOfficeJobDataPipelineFailed
title: BranchOfficeJobDataPipelineFailed
author: windows-driver-content
description: Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler.
old-location: print\branchofficejobdatapipelinefailed.htm
old-project: print
ms.assetid: 3F5DB2F5-40B6-4A8D-983C-065D17E62AE6
ms.author: windowsdriverdev
ms.date: 2/23/2018
ms.keywords: ",  , *, *PBranchOfficeJobDataPipelineFailed, ,, B, BranchOfficeJobDataPipelineFailed, BranchOfficeJobDataPipelineFailed structure [Print Devices], D, F, J, O, P, PBranchOfficeJobDataPipelineFailed, PBranchOfficeJobDataPipelineFailed structure pointer [Print Devices], a, b, c, d, e, f, h, i, l, n, o, p, print.branchofficejobdatapipelinefailed, r, t, winsplp/BranchOfficeJobDataPipelineFailed, winsplp/PBranchOfficeJobDataPipelineFailed"
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
-	BranchOfficeJobDataPipelineFailed
product: Windows
targetos: Windows
req.typenames: BranchOfficeJobDataPipelineFailed, *PBranchOfficeJobDataPipelineFailed
req.product: Windows 10 or later.
---

# BranchOfficeJobDataPipelineFailed structure


## -description


Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler.


## -syntax


````
typedef struct {
  LPWSTR pDocumentName;
  LPWSTR pPrinterName;
  LPWSTR pExtraErrorInfo;
} BranchOfficeJobDataPipelineFailed, *PBranchOfficeJobDataPipelineFailed;
````


## -struct-fields




### -field pDocumentName

Specifies the name of the print document.


### -field pPrinterName

Specifies the print connection.


### -field pExtraErrorInfo

Specifies the name of the client machine printing the job.

