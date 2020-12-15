---
UID: NS:winsplp.__unnamed_struct_3
title: BranchOfficeJobDataPipelineFailed (winsplp.h)
description: Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler.
old-location: print\branchofficejobdatapipelinefailed.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["BranchOfficeJobDataPipelineFailed structure"]
ms.keywords: "*PBranchOfficeJobDataPipelineFailed, BranchOfficeJobDataPipelineFailed, BranchOfficeJobDataPipelineFailed structure [Print Devices], PBranchOfficeJobDataPipelineFailed, PBranchOfficeJobDataPipelineFailed structure pointer [Print Devices], print.branchofficejobdatapipelinefailed, winsplp/BranchOfficeJobDataPipelineFailed, winsplp/PBranchOfficeJobDataPipelineFailed"
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
req.typenames: BranchOfficeJobDataPipelineFailed, *PBranchOfficeJobDataPipelineFailed
f1_keywords:
 - PBranchOfficeJobDataPipelineFailed
 - winsplp/PBranchOfficeJobDataPipelineFailed
 - BranchOfficeJobDataPipelineFailed
 - winsplp/BranchOfficeJobDataPipelineFailed
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - BranchOfficeJobDataPipelineFailed
---

# BranchOfficeJobDataPipelineFailed structure


## -description

Contains the necessary data for logging a branch office job Pipeline Rendering Failed event on a remote server. This is based on standard job-related data available to the spooler.

## -struct-fields

### -field pDocumentName

Specifies the name of the print document.

### -field pPrinterName

Specifies the print connection.

### -field pExtraErrorInfo

Specifies the name of the client machine printing the job.

