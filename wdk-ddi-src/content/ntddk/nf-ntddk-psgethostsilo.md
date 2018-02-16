---
UID: NF:ntddk.PsGetHostSilo
title: PsGetHostSilo function
author: windows-driver-content
description: This routine returns the host silo.
old-location: kernel\psgethostsilo.htm
old-project: kernel
ms.assetid: 0B78562C-25DD-4CF2-9804-6DBEDE8B5F69
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: ntddk/PsGetHostSilo, PsGetHostSilo, PsGetHostSilo routine [Kernel-Mode Driver Architecture], kernel.psgethostsilo
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Windows 10, version 1607
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsGetHostSilo
product: Windows
targetos: Windows
req.typenames: "*PWHEA_RAW_DATA_FORMAT, WHEA_RAW_DATA_FORMAT"
---

# PsGetHostSilo function


## -description


This routine returns the host silo.


## -syntax


````
PESILO PsGetHostSilo(void);
````


## -parameters






## -returns



The host silo.



