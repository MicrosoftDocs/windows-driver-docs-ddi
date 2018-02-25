---
UID: NF:ntddk.PsGetCurrentServerSilo
title: PsGetCurrentServerSilo function
author: windows-driver-content
description: This routine returns the effective server silo for the thread.
old-location: kernel\psgetcurrentserversilo.htm
old-project: kernel
ms.assetid: 4E30CD53-C078-40D7-BEF8-A39F57D71D42
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , C, G, P, PsGetCurrentServerSilo, PsGetCurrentServerSilo routine [Kernel-Mode Driver Architecture], S, e, i, kernel.psgetcurrentserversilo, l, n, ntddk/PsGetCurrentServerSilo, o, r, s, t, u, v"
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
req.irql: "_IRQL_requires_max_(DISPATCH_LEVEL)"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ntddk.h
apiname:
-	PsGetCurrentServerSilo
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsGetCurrentServerSilo function


## -description


This routine returns the effective server silo for the thread.


## -syntax


````
PESILO PsGetCurrentServerSilo(void);
````


## -parameters






## -returns



A pointer to the current server silo.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).



