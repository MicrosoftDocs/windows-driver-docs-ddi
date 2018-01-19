---
UID: NF:ntddk.KeInvalidateAllCaches
title: KeInvalidateAllCaches function
author: windows-driver-content
description: The KeInvalidateAllCaches routine flushes all processor caches.
old-location: kernel\keinvalidateallcaches.htm
old-project: kernel
ms.assetid: a7971cd1-1e9b-4d81-8422-1ee36651973a
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: KeInvalidateAllCaches
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ntddk.h
req.include-header: Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Available in Windows Server 2003 and later versions of Windows.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: KeInvalidateAllCaches
req.alt-loc: NtosKrnl.exe
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
req.typenames: WHEA_RAW_DATA_FORMAT, *PWHEA_RAW_DATA_FORMAT
---

# KeInvalidateAllCaches function



## -description
The <b>KeInvalidateAllCaches</b> routine flushes all processor caches. 



## -syntax

````
BOOLEAN KeInvalidateAllCaches(void);
````


## -parameters


## -returns
<b>KeInvalidateAllCaches</b> returns a value that is reserved for system use. Treat this value as VOID.

<b>KeInvalidateAllCaches</b> returns a value that is reserved for system use. Treat this value as VOID.

<b>KeInvalidateAllCaches</b> returns a value that is reserved for system use. Treat this value as VOID.


## -remarks
The <b>KeInvalidateAllCaches</b> routine flushes each processor's caches and marks each cache's contents invalid. The processor caches are guaranteed to have completed the flush operation before <b>KeInvalidateAllCaches</b> returns.</p>