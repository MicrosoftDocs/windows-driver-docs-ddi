---
UID: NF:ntddk.PsGetCurrentSilo
title: PsGetCurrentSilo function (ntddk.h)
description: This routine returns the current silo for the calling thread. First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo.
old-location: kernel\psgetcurrentsilo.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsGetCurrentSilo function"]
ms.keywords: PsGetCurrentSilo, PsGetCurrentSilo routine [Kernel-Mode Driver Architecture], kernel.psgetcurrentsilo, ntddk/PsGetCurrentSilo
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
req.irql: _IRQL_requires_max_(DISPATCH_LEVEL)
targetos: Windows
req.typenames: 
f1_keywords:
 - PsGetCurrentSilo
 - ntddk/PsGetCurrentSilo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetCurrentSilo
---

# PsGetCurrentSilo function


## -description

This routine returns the current silo for the calling thread.  First the thread is checked to see if it has been attached to a silo. If not, then the thread is checked to see if it is in a silo.

## -parameters

## -returns

A pointer to the <b>ESILO</b> object.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).

