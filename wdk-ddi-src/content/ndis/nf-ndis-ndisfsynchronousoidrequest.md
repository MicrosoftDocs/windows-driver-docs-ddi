---
UID: NF:ndis.NdisFSynchronousOidRequest
title: NdisFSynchronousOidRequest function
description: Filter drivers call the NdisFSynchronousOidRequest function to originate a new Synchronous OID request and issue it to underlying drivers.
old-location: netvista\ndisfsynchronousoidrequest.htm
tech.root: netvista
ms.assetid: 01B625EB-AB6D-496F-95F2-22845460324A
ms.date: 05/02/2018
ms.keywords: NdisFSynchronousOidRequest, NdisFSynchronousOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFSynchronousOidRequest, netvista.ndisfsynchronousoidrequest
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Windows 10, version 1709
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisFSynchronousOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFSynchronousOidRequest function


## -description

Filter drivers call the NdisFSynchronousOidRequest function to originate a new Synchronous OID request and issue it to underlying drivers.

This function is supported in NDIS 6.81 and later.

## -parameters


### -param NdisFilterModuleHandle [in]

An NDIS handle that identifies a filter module. NDIS passed the handle to the filter driver in a call to the [*FilterAttach*](nc-ndis-filter_attach.md) function.

### -param OidRequest [in]

A pointer to an [**NDIS_OID_REQUEST**](ns-ndis-_ndis_oid_request.md) structure that specifies the operation that is requested with a given *OID_Xxx* code. The structure can specify an OID query, set, or method request.

## -returns

This function returns the same values as [**NdisDirectOidRequest**](nf-ndis-ndisdirectoidrequest.md) **except** that NDIS_STATUS_PENDING is never returned from this function.

## -remarks

The **NdisFSynchronousOidRequest** function cannot be used for general OID requests. For general OID requests, use the [**NdisFOidRequest**](nf-ndis-ndisfoidrequest.md) function instead. **NdisFSynchronousOidRequest** can be used only for OIDs that NDIS supports for use with the Synchronous OID interface. Most filter drivers do not need to call **NdisFSynchronousOidRequest**.

Filter drivers must not complete [*FilterDetach*](nc-ndis-filter_detach.md) until any Synchronous OID requests originated by the filter driver are completed.

Filter drivers are not required to implement [*FilterOidRequestComplete*](nc-ndis-filter_oid_request_complete.md), [*FilterDirectOidRequestComplete*](nc-ndis-filter_direct_oid_request_complete.md), [*FilterSynchronousOidRequest*](nf-ndis-filter_synchronous_oid_request.md), or [*FilterSynchronousOidRequestComplete*](nf-ndis-filter_synchronous_oid_request_complete.md) in order to call **NdisFSynchronousOidRequest**. As its name suggests, a Synchronous OID request always completes synchronously, so there is no asynchronous callback.

## -see-also

[*FilterSynchronousOidRequest*](nf-ndis-filter_synchronous_oid_request.md)

[*FilterSynchronousOidRequestComplete*](nf-ndis-filter_synchronous_oid_request_complete.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
