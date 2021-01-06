---
UID: NF:ndis.NDIS_WAIT_FOR_MUTEX
title: NDIS_WAIT_FOR_MUTEX macro (ndis.h)
description: The NDIS_WAIT_FOR_MUTEX macro puts the current thread into the wait state until the specified mutex object is set to the signaled state.
tech.root: netvista
ms.date: 04/16/2018
keywords: ["NDIS_WAIT_FOR_MUTEX macro"]
ms.keywords: NDIS_WAIT_FOR_MUTEX
req.header: ndis.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.ddi-compliance: Irql_Synch_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - NDIS_WAIT_FOR_MUTEX
 - ndis/NDIS_WAIT_FOR_MUTEX
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ndis.h
api_name:
 - NDIS_WAIT_FOR_MUTEX
---

# NDIS_WAIT_FOR_MUTEX macro


## -description

The **NDIS_WAIT_FOR_MUTEX** macro puts the current thread into the wait state until the specified mutex object is set to the signaled state.

## -parameters

### -param _M_

A pointer to an initialized NDIS_MUTEX-type mutex object. The caller initialized the mutex object in a prior call to the [**NDIS_INIT_MUTEX**](nf-ndis-ndis_init_mutex.md) macro. NDIS_MUTEX is a wrapper for the KMUTEX type.

## -returns

**NDIS_WAIT_FOR_MUTEX** returns STATUS_SUCCESS if the operation completed successfully. Otherwise, it returns an appropriate NTSTATUS error code.

## -remarks

NDIS network drivers should use the **NDIS_WAIT_FOR_MUTEX** macro to wait for a mutex to transition to the signaled state.

A driver cannot wait for a nonzero time interval on a mutex object at a raised IRQL or in an *arbitrary thread context* (that is, the context of whatever thread is current when a driver function is called).

**NDIS_WAIT_FOR_MUTEX** examines the current state of the mutex object to determine if the wait operation can be satisfied immediately. If the operation can be satisfied immediately, the necessary updates are made to mutex object. Otherwise, the current thread is in a waiting state, and a new thread is selected for execution on the current processor.

This macro is an NDIS wrapper for the [**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md) routine.

Callers of **NDIS_WAIT_FOR_MUTEX** must be running at IRQL == PASSIVE_LEVEL and in a nonarbitrary thread context.

## -see-also

[**KeWaitForSingleObject**](../wdm/nf-wdm-kewaitforsingleobject.md)

[**NDIS_INIT_MUTEX**](nf-ndis-ndis_init_mutex.md)

[**NDIS_RELEASE_MUTEX**](nf-ndis-ndis_release_mutex.md)

