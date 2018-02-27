---
UID: NF:ntddk.PsTerminateServerSilo
title: PsTerminateServerSilo function
author: windows-driver-content
description: This routine terminates the specified silo.
old-location: kernel\psterminateserversilo.htm
old-project: kernel
ms.assetid: C19190A3-57F9-4482-A550-045805734909
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: PsTerminateServerSilo, PsTerminateServerSilo routine [Kernel-Mode Driver Architecture], kernel.psterminateserversilo, ntddk/PsTerminateServerSilo
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
-	PsTerminateServerSilo
product: Windows
targetos: Windows
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# PsTerminateServerSilo function


## -description


This routine terminates the specified silo.


## -syntax


````
void PsTerminateServerSilo(
  _In_ PESILO   ServerSilo,
  _In_ NTSTATUS ExistStatus
);
````


## -parameters




### -param ServerSilo [in]

A pointer to the silo being terminated.


### -param ExitStatus

TBD




#### - ExistStatus [in]

The exit status for the silo.


## -returns



This routine does not return a value.




## -remarks



This routine can be called within or from outside a silo context.
    Note that this is different from a BugCheck; this routine will return to
    the caller.



