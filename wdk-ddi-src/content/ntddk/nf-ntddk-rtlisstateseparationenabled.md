---
UID: NF:ntddk.RtlIsStateSeparationEnabled
title: RtlIsStateSeparationEnabled function
author: windows-driver-content
description: Checks if the SKU for the current context supports multiple sessions.
old-location: kernel\rtlisstateseparationenabled.htm
old-project: kernel
ms.assetid: 7c28a82c-e039-4045-94cd-b47a45d15e28
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: RtlIsStateSeparationEnabled, ntddk/RtlIsStateSeparationEnabled, RtlIsStateSeparationEnabled function [Kernel-Mode Driver Architecture], kernel.rtlisstateseparationenabled
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe (kernel mode)
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	NtosKrnl.exe
apiname:
-	RtlIsStateSeparationEnabled
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# RtlIsStateSeparationEnabled function


## -description



			
            Checks if the SKU for the current context supports multiple
    sessions.



## -syntax


````
 BOOLEAN  RtlIsStateSeparationEnabled(
   VOID 
);
````


## -parameters





## -returns


 TRUE indicates state separation enabled;

    FALSE otherwise.


