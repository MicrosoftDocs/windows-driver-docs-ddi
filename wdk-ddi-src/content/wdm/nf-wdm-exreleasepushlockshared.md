---
UID: NF:wdm.ExReleasePushLockShared
title: ExReleasePushLockShared macro
author: windows-driver-content
description: Releases a specified push lock for shared access owned by the current thread.
ms.assetid: 261e7340-9015-4c58-a52e-87d563c7c884
ms.author: windowsdriverdev
ms.date: 09/18/2018
ms.topic: macro
ms.keywords: ExReleasePushLockShared
req.header: wdm.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
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
-	ExReleasePushLockShared
product: Windows
targetos: Windows


---

# ExReleasePushLockShared macro


## -description

Releases a specified push lock for shared access owned by the current thread.

## -parameters

### -param Lock
Opaque push lock pointer specified in the [**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md) call. This pointer must have been initialized by a previous call to [**ExInitializePushLock**](nf-wdm-exinitializepushlock.md).


## -remarks

To acquire a push lock for exclusive access, call [**ExAcquirePushLockExclusive**](nf-wdm-exacquirepushlockexclusive.md).

To acquire a push lock for shared access, call [**ExAcquirePushLockShared**](nf-wdm-exacquirepushlockshared.md).

## -see-also