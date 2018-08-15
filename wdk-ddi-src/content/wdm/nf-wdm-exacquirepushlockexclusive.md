---
UID: NF:wdm.ExAcquirePushLockExclusive
title: ExAcquirePushLockExclusive macro
author: windows-driver-content
description: Acquires the given push lock for exclusive access by the calling thread.
ms.assetid: ba752619-f885-4977-b0e6-7c0339373b78
ms.author: windowsdriverdev
ms.date: 
ms.topic: macro
ms.keywords: ExAcquirePushLockExclusive
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: 
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library: 
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	wdm.h
api_name: 
-	ExAcquirePushLockExclusive
product: Windows
targetos: Windows


---

# ExAcquirePushLockExclusive macro


## -description

Acquires the given push lock for exclusive access by the calling thread.

## -parameters

### -param Lock
Opaque push lock pointer. This pointer must have been initialized by a previous call to [**FltInitializePushLock**](nf-wdm-exinitializepushlock.md).

## -remarks
The caller is required call KeEnter/LeaveCriticalRegion before calling FltAcquirePushLockExclusive. 

## -see-also