---
UID: NF:ntddk.PsGetCurrentServerSilo
title: PsGetCurrentServerSilo function (ntddk.h)
description: This routine returns the effective server silo for the thread.
old-location: kernel\psgetcurrentserversilo.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["PsGetCurrentServerSilo function"]
ms.keywords: PsGetCurrentServerSilo, PsGetCurrentServerSilo routine [Kernel-Mode Driver Architecture], kernel.psgetcurrentserversilo, ntddk/PsGetCurrentServerSilo
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
 - PsGetCurrentServerSilo
 - ntddk/PsGetCurrentServerSilo
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - PsGetCurrentServerSilo
---

# PsGetCurrentServerSilo function


## -description

This routine returns the effective server silo for the thread.

## -returns

A pointer to the current server silo.  This pointer is valid for the current thread, but must be referenced before transferring to another thread (for example, via a workitem).

