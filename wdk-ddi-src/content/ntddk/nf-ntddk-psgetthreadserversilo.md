---
UID: NF:ntddk.PsGetThreadServerSilo
title: PsGetThreadServerSilo function (ntddk.h)
description: Determines whether the given thread is a silo.
tech.root: kernel
ms.date: 09/30/2018
keywords: ["PsGetThreadServerSilo function"]
ms.keywords: PsGetThreadServerSilo
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: Ntoskrnl.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
ms.custom: RS5
f1_keywords:
 - PsGetThreadServerSilo
 - ntddk/PsGetThreadServerSilo
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - Ntoskrnl.exe
api_name:
 - PsGetThreadServerSilo
---

# PsGetThreadServerSilo function


## -description

Determines whether the given thread is a silo.

## -parameters

### -param Thread [In]

A pointer to the thread being examined.

## -returns

Returns a pointer to the server silo for the thread or NULL.

## -remarks

## -see-also

