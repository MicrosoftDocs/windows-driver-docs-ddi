---
UID: NF:winsplp.LogJobInfoForBranchOffice
title: LogJobInfoForBranchOffice function
author: windows-driver-content
description: Allows Branch Office clients to send job events to the host print server.
old-location: print\logjobinfoforbranchoffice.htm
old-project: print
ms.assetid: 6D1AB299-2E26-42AF-9613-CA321173080D
ms.author: windowsdriverdev
ms.date: 1/8/2018
ms.keywords: LogJobInfoForBranchOffice
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: winsplp.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: LogJobInfoForBranchOffice
req.alt-loc: Winsplp.h
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
req.typenames: NOTIFICATION_CONFIG_FLAGS
req.product: Windows 10 or later.
---

# LogJobInfoForBranchOffice function



## -description
Allows Branch Office clients to send job events to the host print server.



## -syntax

````
HRESULT WINAPI LogJobInfoForBranchOffice(
  _In_ HANDLE                        hPrinter,
  _In_ PBranchOfficeJobDataContainer pJobDataContainer
);
````


## -parameters

### -param hPrinter [in]

Specifies a handle to the CSR printer.


### -param pJobDataContainer [in]

Specifies a pointer to an array of <a href="RID">BranchOfficeJobData</a> structures, containing the events to be logged.


## -returns
Indicates success or failure.


## -remarks
