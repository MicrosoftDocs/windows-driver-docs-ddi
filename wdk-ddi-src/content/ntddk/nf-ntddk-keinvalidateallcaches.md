---
UID: NF:ntddk.KeInvalidateAllCaches
title: KeInvalidateAllCaches function (ntddk.h)
description: The KeInvalidateAllCaches routine flushes all processor caches.
old-location: kernel\keinvalidateallcaches.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["KeInvalidateAllCaches function"]
ms.keywords: KeInvalidateAllCaches, KeInvalidateAllCaches routine [Kernel-Mode Driver Architecture], k105_4b59c5bd-70e3-48e1-aa6c-abf4e02925e8.xml, kernel.keinvalidateallcaches, ntddk/KeInvalidateAllCaches
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - KeInvalidateAllCaches
 - ntddk/KeInvalidateAllCaches
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - KeInvalidateAllCaches
---

# KeInvalidateAllCaches function


## -description

The <b>KeInvalidateAllCaches</b> routine flushes all processor caches.

## -returns

<b>KeInvalidateAllCaches</b> returns a value that is reserved for system use. Treat this value as VOID.

## -remarks

The <b>KeInvalidateAllCaches</b> routine flushes each processor's caches and marks each cache's contents invalid. The processor caches are guaranteed to have completed the flush operation before <b>KeInvalidateAllCaches</b> returns.

