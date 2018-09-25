---
UID: NF:ndis.NDIS_RELEASE_MUTEX
title: NDIS_RELEASE_MUTEX macro
author: windows-driver-content
description: The NDIS_RELEASE_MUTEX macro releases the specified mutex object.
ms.assetid: 9a64c6fc-ee2c-45b5-ba12-7e9a42934a9b
ms.author: windowsdriverdev
ms.date: 04/16/2018
ms.topic: macro
ms.keywords: NDIS_RELEASE_MUTEX
req.header: ndis.h
req.include-header:
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
req.ddi-compliance: Irql_Synch_Function
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
-	NDIS_RELEASE_MUTEX
product:
-	Windows
targetos: Windows

---

# NDIS_RELEASE_MUTEX macro


## -description

The NDIS_RELEASE_MUTEX macro releases the specified mutex object.

## -parameters

### -param _M_

A pointer to an initialized NDIS_MUTEX-type mutex object. The caller initialized the mutex object in a prior call to the [**NDIS_INIT_MUTEX**](nf-ndis-ndis_init_mutex.md) macro. NDIS_MUTEX is a wrapper for the KMUTEX type.

## -returns

**NDIS_RELEASE_MUTEX** returns a LONG value. If the return value is zero, the mutex object was released and is in the signaled state. If **NDIS_RELEASE_MUTEX** returns a nonzero value, the mutex is not in the signaled state.

## -remarks

NDIS network drivers should use the **NDIS_RELEASE_MUTEX** macro to release a mutex.

Only the thread that is currently holding the mutex object can release it. Otherwise, a bugcheck occurs. A bugcheck also occurs if a driver attempts to release a mutex object that is in the signaled state.

To acquire the mutex, call the [**NDIS_WAIT_FOR_MUTEX**](nf-ndis-ndis_wait_for_mutex.md) macro. If a mutex is acquired recursively, the holding thread must call **NDIS_RELEASE_MUTEX** the same number of times that it acquired the mutex to set it back to the signaled state.

**NDIS_RELEASE_MUTEX** is an NDIS wrapper for the [**KeReleaseMutex**](../wdm/nf-wdm-kereleasemutex.md) routine.

## -see-also

[**KeReleaseMutex**](../wdm/nf-wdm-kereleasemutex.md)

[**NDIS_INIT_MUTEX**](nf-ndis-ndis_init_mutex.md)

[**NDIS_WAIT_FOR_MUTEX**](nf-ndis-ndis_wait_for_mutex.md)