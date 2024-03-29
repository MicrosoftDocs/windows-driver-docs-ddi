---
UID: NS:winsplp.BranchOfficeJobData
title: BranchOfficeJobData (winsplp.h)
description: This structure contains the type of event to log (eEventType), the job ID, and the data required by the event.
old-location: print\branchofficejobdata.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["BranchOfficeJobData structure"]
ms.keywords: "*PBranchOfficeJobData, BranchOfficeJobData, BranchOfficeJobData structure [Print Devices], PBranchOfficeJobData, PBranchOfficeJobData structure pointer [Print Devices], print.branchofficejobdata, winsplp/BranchOfficeJobData, winsplp/PBranchOfficeJobData"
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
targetos: Windows
req.typenames: BranchOfficeJobData, *PBranchOfficeJobData
f1_keywords:
 - PBranchOfficeJobData
 - winsplp/PBranchOfficeJobData
 - BranchOfficeJobData
 - winsplp/BranchOfficeJobData
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - PBranchOfficeJobData
 - BranchOfficeJobData
---

# BranchOfficeJobData structure


## -description

This structure contains the type of event to log (eEventType), the job ID, and the data required by the event.

## -struct-fields

### -field eEventType

Specifies the type of event to be logged.

### -field JobId

Specifies the ID of the job on the client.

### -field JobInfo

### -field JobInfo.LogJobPrinted

Describes  the <b>BranchOfficeJobDataPrinted</b> type member <b>LogJobPrinted</b>.

### -field JobInfo.LogJobRendered

Describes the <b>BranchOfficeJobDataRendered</b> type member <b>LogJobRendered</b>.

### -field JobInfo.LogJobError

Describes the <b>BranchOfficeJobDataError</b> type member <b>LogJobError</b>.

### -field JobInfo.LogPipelineFailed

Describes the <b>BranchOfficeJobDataPipelineFailed</b> type member <b>LogPipelineFailed</b>.

### -field JobInfo.LogOfflineFileFull

Describes the <b>BranchOfficeLogOfflineFileFull</b> type member <b>LogOfflineFileFull</b>.

