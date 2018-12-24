---
UID: NF:ntddk.PsTerminateServerSilo
title: PsTerminateServerSilo function
description: This routine terminates the specified silo.
old-location: kernel\psterminateserversilo.htm
tech.root: kernel
ms.assetid: C19190A3-57F9-4482-A550-045805734909
ms.date: 04/30/2018
ms.keywords: PsTerminateServerSilo, PsTerminateServerSilo routine [Kernel-Mode Driver Architecture], kernel.psterminateserversilo, ntddk/PsTerminateServerSilo
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddk.h
api_name:
-	PsTerminateServerSilo
product:
- Windows
targetos: Windows
req.typenames: 
---

# PsTerminateServerSilo function


## -description


This routine terminates the specified silo.


## -parameters




### -param ServerSilo [in]

A pointer to the silo being terminated.


### -param ExitStatus

<p>The exit status for the silo.</p>




## -returns



This routine does not return a value.




## -remarks



This routine can be called within or from outside a silo context.
    Note that this is different from a BugCheck; this routine will return to
    the caller.



