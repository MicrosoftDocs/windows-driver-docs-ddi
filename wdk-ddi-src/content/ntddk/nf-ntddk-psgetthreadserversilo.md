---
UID: NF:ntddk.PsGetThreadServerSilo
title: PsGetThreadServerSilo function (ntddk.h)
description: Determines whether the given thread is a silo.
tech.root: kernel
ms.assetid: 021c4a39-c2fd-4f6d-8299-0f36fab0a69f
ms.date: 09/30/2018
tech.root: kernel
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

### -param Thread

[In] A pointer to the job being examined.

## -returns

Returns TRUE if the job is a silo, FALSE otherwise.

## -remarks

## -see-also

