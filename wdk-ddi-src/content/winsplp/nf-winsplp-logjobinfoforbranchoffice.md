---
UID: NF:winsplp.LogJobInfoForBranchOffice
title: LogJobInfoForBranchOffice function (winsplp.h)
description: Allows Branch Office clients to send job events to the host print server.
old-location: print\logjobinfoforbranchoffice.htm
tech.root: print
ms.date: 04/20/2018
keywords: ["LogJobInfoForBranchOffice function"]
ms.keywords: LogJobInfoForBranchOffice, LogJobInfoForBranchOffice function [Print Devices], print.logjobinfoforbranchoffice, winsplp/LogJobInfoForBranchOffice
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
req.typenames: 
f1_keywords:
 - LogJobInfoForBranchOffice
 - winsplp/LogJobInfoForBranchOffice
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Winsplp.h
api_name:
 - LogJobInfoForBranchOffice
---

# LogJobInfoForBranchOffice function


## -description

Allows Branch Office clients to send job events to the host print server.

## -parameters

### -param hPrinter 

[in]
Specifies a handle to the CSR printer.

### -param pJobDataContainer 

[in]
Specifies a pointer to an array of <a href="/dotnet/core/rid-catalog">BranchOfficeJobData</a> structures, containing the events to be logged.

## -returns

Indicates success or failure.
