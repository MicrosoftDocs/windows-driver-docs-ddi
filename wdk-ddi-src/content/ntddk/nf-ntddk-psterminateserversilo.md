---
UID: NF:ntddk.PsTerminateServerSilo
title: PsTerminateServerSilo function (ntddk.h)
description: This routine terminates the specified silo.
old-location: kernel\psterminateserversilo.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsTerminateServerSilo function"]
ms.keywords: PsTerminateServerSilo, PsTerminateServerSilo routine [Kernel-Mode Driver Architecture], kernel.psterminateserversilo, ntddk/PsTerminateServerSilo
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
targetos: Windows
req.typenames: 
f1_keywords:
 - PsTerminateServerSilo
 - ntddk/PsTerminateServerSilo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsTerminateServerSilo
---

# PsTerminateServerSilo function


## -description

This routine terminates the specified silo.

## -parameters

### -param ServerSilo 

[in]
A pointer to the silo being terminated.

### -param ExitStatus

<p>The exit status for the silo.</p>

## -remarks

This routine can be called within or from outside a silo context.
    Note that this is different from a BugCheck; this routine will return to
    the caller.

