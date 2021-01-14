---
UID: NF:ndis.FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
title: FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function (ndis.h)
description: NDIS calls a filter driver’s FilterSynchronousOidRequestComplete function after a Synchronous OID request has been completed from an underlying driver.
old-location: netvista\filter_synchronous_oid_request_complete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function"]
ms.keywords: FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE, FilterSynchronousOidRequestComplete, FilterSynchronousOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/FilterSynchronousOidRequestComplete, netvista.filter_synchronous_oid_request_complete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
 - ndis/FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Ndis.h
api_name:
 - FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE
---

# FILTER_SYNCHRONOUS_OID_REQUEST_COMPLETE function


## -description

NDIS calls a filter driver’s FilterSynchronousOidRequestComplete function after a Synchronous OID request has been completed from an underlying driver.

This function is supported in NDIS 6.81 and later.

## -parameters

### -param FilterModuleContext 

[in]
A handle to the context area for the filter module that is the target of this request. The filter driver created and initialized this context area in the [*FilterAttach*](nc-ndis-filter_attach.md) function.

### -param OidRequest 

[in, out]
A pointer to an [**NDIS_OID_REQUEST**](ns-ndis-_ndis_oid_request.md) structure that specifies the operation being completed.

### -param Status 

[in, out]
A pointer to the resulting status code of the request being completed.

### -param CallContext 

[in]
A PVOID-sized storage slot for the filter driver to share state between its [*FilterSynchronousOidRequest*](nf-ndis-filter_synchronous_oid_request.md) and *FilterSynchronousOidRequestComplete* handlers. If the filter driver implements a *FilterSynchronousOidRequest* handler, this parameter contains the context value that the *FilterSynchronousOidRequest* handler returned. Otherwise, if the filter driver does not implement a *FilterSynchronousOidRequest* handler, this value is zero.

## -remarks

*FilterSynchronousOidRequestComplete* is an optional function. If a filter driver does not need to observe or modify Synchronous OID requests completed from the miniport driver, the filter driver should set the entry point for this function to **NULL** when it calls [**NdisFRegisterFilterDriver**](nf-ndis-ndisfregisterfilterdriver.md).

NDIS calls the filter driver’s *FilterSynchronousOidRequestComplete* function to process Synchronous OID requests that are completed by underlying drivers. Filter drivers can read or modify some fields in the [**NDIS_OID_REQUEST**](ns-ndis-_ndis_oid_request.md) structure as follows:

| Field | Filter access |
| --- | --- |
| Header | Read-only |
| RequestType | Read/write |
| PortNumber | Read/write |
| Timeout | Do not access |
| RequestId | Do not access |
| RequestHandle | Read/write |
| DATA | Read/write |
| NdisReserved | Do not access |
| MiniportReserved | Do not access |
| SourceReserved | Do not access |
| SupportedRevision | Read/write |
| Reserved1, Reserved2 | Do not access |
| SwitchId | Read/write |
| VPortId | Read/write |
| Flags | Read/write |

In addition to modifying the **NDIS_OID_REQUEST** structure, filter drivers can read or modify the status code with which the operation completed. The filter driver can write a new value to the _*Status_ parameter. Filter drivers must not write NDIS_STATUS_PENDING or NDIS_STATUS_ALREADY_COMPLETE to the _*Status_ parameter.

If the filter driver also registers a [*FilterSynchronousOidRequest*](nf-ndis-filter_synchronous_oid_request.md) handler, NDIS guarantees that the *FilterSynchronousOidRequestComplete* handler will be called if and only if the *FilterSynchronousOidRequest* handler returns NDIS_STATUS_SUCCESS.

Filter drivers are expected to return from their *FilterSynchronousOidRequestComplete* handler quickly, without blocking, waiting, or sleeping. Synchronous OID requests are only used for low-latency operations, and filter drivers should strive to continue or complete them within several milliseconds.

NDIS does not serialize Synchronous OID requests against each other, against other OID requests, or against [*FilterPause*](nc-ndis-filter_pause.md). It is the responsibility of the filter driver to implement any needed synchronization.

NDIS does serialize Synchronous OID requests against [*FilterDetach*](nc-ndis-filter_detach.md): NDIS guarantees that no Synchronous OID requests will be active once *FilterDetach* is invoked.

Filter drivers must not call [**NdisAllocateCloneOidRequest**](nf-ndis-ndisallocatecloneoidrequest.md) or [**NdisCancelOidRequest**](nf-ndis-ndiscanceloidrequest.md) on a Synchronous OID request. Filter drivers must not call [**NdisFSynchronousOidRequest**](nf-ndis-ndisfsynchronousoidrequest.md) on an OID request that is received through a *FilterSynchronousOidRequestComplete* handler.

## -see-also

[*FilterSynchronousOidRequest*](nf-ndis-filter_synchronous_oid_request.md)

[**NdisFSynchronousOidRequest**](nf-ndis-ndisfsynchronousoidrequest.md)

[Synchronous OID Request Interface in NDIS 6.80](/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80)

