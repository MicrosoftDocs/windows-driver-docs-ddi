---
UID: NF:winsplp.LogJobInfoForBranchOffice
title: LogJobInfoForBranchOffice function
author: windows-driver-content
description: Allows Branch Office clients to send job events to the host print server.
old-location: print\logjobinfoforbranchoffice.htm
old-project: print
ms.assetid: 6D1AB299-2E26-42AF-9613-CA321173080D
ms.author: windowsdriverdev
ms.date: 2/21/2018
ms.keywords: LogJobInfoForBranchOffice, LogJobInfoForBranchOffice function [Print Devices], print.logjobinfoforbranchoffice, winsplp/LogJobInfoForBranchOffice
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
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.exe
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
-	LogJobInfoForBranchOffice
product: Windows
targetos: Windows
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

Specifies a pointer to an array of <a href="https://docs.microsoft.com/en-us/dotnet/core/rid-catalog">BranchOfficeJobData</a> structures, containing the events to be logged.


## -returns



Indicates success or failure.



