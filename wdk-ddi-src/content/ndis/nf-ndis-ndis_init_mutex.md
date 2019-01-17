---
UID: NF:ndis.NDIS_INIT_MUTEX
title: NDIS_INIT_MUTEX macro
description: The NDIS_INIT_MUTEX macro initializes a mutex object and sets it to a signaled state.
tech.root: netvista
ms.assetid: b55ee6e6-ae83-43fb-af92-1f005057d4ae
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_INIT_MUTEX
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: Any level
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
-	ndis.h
api_name: 
-	NDIS_INIT_MUTEX
product:
-	Windows
targetos: Windows

---

# NDIS_INIT_MUTEX macro


## -description

The **NDIS_INIT_MUTEX** macro initializes a mutex object and sets it to a signaled state.

## -parameters

### -param _M_

A pointer to a caller-supplied NDIS_MUTEX-type mutex object. NDIS_MUTEX is a wrapper for KMUTEX.

## -returns

This macro does not return a value.

## -remarks

NDIS network drivers should use the **NDIS_INIT_MUTEX** macro to initialize a mutex.

The initial state of the mutex object is the signaled state. To acquire the mutex, call the [**NDIS_WAIT_FOR_MUTEX**](nf-ndis-ndis_wait_for_mutex.md) macro. To release the mutex, call the [**NDIS_RELEASE_MUTEX**](nf-ndis-ndis_release_mutex.md) macro.

A driver cannot wait for a nonzero time interval on a mutex object at a raised IRQL or in an *arbitrary thread context* (that is, the context of whatever thread is current when a driver function is called).

Storage for a mutex object must reside in a driver context area or in a nonpaged pool that the caller allocated.

The **NDIS_INIT_MUTEX** macro is an NDIS wrapper for the [**KeInitializeMutex**](../wdm/nf-wdm-keinitializemutex.md) routine.

## -see-also

[**KeInitializeMutex**](../wdm/nf-wdm-keinitializemutex.md)

[**NDIS_RELEASE_MUTEX**](nf-ndis-ndis_release_mutex.md)

[**NDIS_WAIT_FOR_MUTEX**](nf-ndis-ndis_wait_for_mutex.md)
