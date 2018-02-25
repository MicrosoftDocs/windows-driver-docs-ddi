---
UID: NS:winsplp.BranchOfficeJobData
title: BranchOfficeJobData
author: windows-driver-content
description: This structure contains the type of event to log (eEventType), the job ID, and the data required by the event.
old-location: print\branchofficejobdata.htm
old-project: print
ms.assetid: B49FEED5-C90A-4E4F-9B73-E06E56FB4311
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , *, *PBranchOfficeJobData, ,, B, BranchOfficeJobData, BranchOfficeJobData structure [Print Devices], D, J, O, P, PBranchOfficeJobData, PBranchOfficeJobData structure pointer [Print Devices], a, b, c, e, f, h, i, n, o, print.branchofficejobdata, r, t, winsplp/BranchOfficeJobData, winsplp/PBranchOfficeJobData"
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
-	BranchOfficeJobData
product: Windows
targetos: Windows
req.typenames: BranchOfficeJobData, *PBranchOfficeJobData
req.product: Windows 10 or later.
---

# BranchOfficeJobData structure


## -description


This structure contains the type of event to log (eEventType), the job ID, and the data required by the event.


## -syntax


````
typedef struct {
  EBranchOfficeJobEventType eEventType;
  DWORD                     JobId;
  union {
    BranchOfficeJobDataPrinted        LogJobPrinted;
    BranchOfficeJobDataRendered       LogJobRendered;
    BranchOfficeJobDataError          LogJobError;
    BranchOfficeJobDataPipelineFailed LogPipelineFailed;
    BranchOfficeLogOfflineFileFull    LogOfflineFileFull;
  } JobInfo;
} BranchOfficeJobData, *PBranchOfficeJobData;
````


## -struct-fields




### -field eEventType

Specifies the type of event to be logged.


### -field JobId

Specifies the ID of the job on the client.


### -field JobInfo



#### LogJobPrinted

Describes  the <b>BranchOfficeJobDataPrinted</b> type member <b>LogJobPrinted</b>.



#### LogJobRendered

Describes the <b>BranchOfficeJobDataRendered</b> type member <b>LogJobRendered</b>.



#### LogJobError

Describes the <b>BranchOfficeJobDataError</b> type member <b>LogJobError</b>.



#### LogPipelineFailed

Describes the <b>BranchOfficeJobDataPipelineFailed</b> type member <b>LogPipelineFailed</b>.



#### LogOfflineFileFull

Describes the <b>BranchOfficeLogOfflineFileFull</b> type member <b>LogOfflineFileFull</b>.

