---
UID: NF:ndis.FILTER_SYNCHRONOUS_OID_REQUEST
title: FILTER_SYNCHRONOUS_OID_REQUEST function (ndis.h)
description: NDIS calls a filter driver's FilterSynchronousOidRequest function to preview a Synchronous OID request before the request is given to the underlying miniport driver.
old-location: netvista\filter_synchronous_oid_request.htm
tech.root: netvista
ms.assetid: AC84B27B-6FBF-429D-A8FA-F3C8F583F738
ms.date: 05/02/2018
keywords: ["FILTER_SYNCHRONOUS_OID_REQUEST function"]
ms.keywords: FILTER_SYNCHRONOUS_OID_REQUEST, FilterSynchronousOidRequest, FilterSynchronousOidRequest function [Network Drivers Starting with Windows Vista], ndis/FilterSynchronousOidRequest, netvista.filter_synchronous_oid_request
f1_keywords:
 - "ndis/FilterSynchronousOidRequest"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Ndis.h
api_name:
- FilterSynchronousOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# FILTER_SYNCHRONOUS_OID_REQUEST function


## -description

NDIS calls a filter driver's *FilterSynchronousOidRequest* function to preview a Synchronous OID request before the request is given to the underlying miniport driver.

This function is supported in NDIS 6.81 and later.

## -parameters


### -param FilterModuleContext

A handle to the context area for the filter module that is the target of this request. The filter driver created and initialized this context area in the [**FilterAttach**](nc-ndis-filter_attach.md) function.

### -param OidRequest [in, out]

A pointer to an [**NDIS_OID_REQUEST**](ns-ndis-_ndis_oid_request.md) structure that specifies the operation requested.


### -param CallContext [out]

A PVOID-sized storage slot for the filter driver to share state between its *FilterSynchronousOidRequest* and [*FilterSynchronousOidRequestComplete*](nf-ndis-filter_synchronous_oid_request_complete.md) handlers. NDIS guarantees this initially points to a zero value. See the Remarks section for more information. 

## -returns

This function returns one of the following appropriate NDIS_STATUS codes:

| Return code | Description |
| --- | --- |
| NDIS_STATUS_SUCCESS | Allow the OID request to continue propagating down to the miniport driver. Filter drivers must return this status code for any unrecognized type of OID. |
| NDIS_STATUS_ALREADY_COMPLETE | Stop propagating the OID request down, and instead return it to the caller with the status NDIS_STATUS_SUCCESS. |
| <ul><li>NDIS_STATUS_BUFFER_TOO_SHORT</li><li>NDIS_STATUS_INVALID_LENGTH</li><li>NDIS_STATUS_INVALID_DATA</li></ul> | Same as [*FilterDirectOidRequest*](nc-ndis-filter_direct_oid_request.md). |
| NDIS_STATUS_RESOURCES | Same as *FilterDirectOidRequest*, but with a caution that Synchronous OID requests must be completed quickly, and so filter drivers should typically avoid allocating resources. |
| NDIS_STATUS_NOT_SUPPORTED | Filter drivers must not return this code simply because the OID is unrecognized. Filter drivers may only return this if the filter recognizes the operation but cannot perform it for some reason. |

## -remarks

*FilterSynchronousOidRequest* is an optional function. If a filter driver does not need to observe or modify Synchronous OID requests sent to the miniport driver, the filter driver should set the entry point for this function to **NULL** when it calls [**NdisFRegisterFilterDriver**](nf-ndis-ndisfregisterfilterdriver.md).

NDIS calls the filter driver’s *FilterSynchronousOidRequest* function to process Synchronous OID requests that are originated by overlying drivers. Filter drivers can read or modify some fields in the [**NDIS_OID_REQUEST**](ns-ndis-_ndis_oid_request.md) structure as follows:

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

In addition to modifying the **NDIS_OID_REQUEST** structure, filter drivers can control the request using the return code from *FilterSynchronousOidRequest*:

- NDIS_STATUS_SUCCESS: the OID continues to propagate down to the miniport driver.
- NDIS_STATUS_ALREADY_COMPLETE: the OID is immediately completed back to the overlying drivers, without first propagating down to the miniport driver. The OID request is completed to the overlying driver with NDIS_STATUS_SUCCESS.
- Any other status code: the OID is immediately completed back to the overlying drivers, without first propagating down to the miniport driver. The OID request is completed to the overlying driver with the status code returned by the filter driver.

If the filter driver also registers a [*FilterSynchronousOidRequestComplete*](nf-ndis-filter_synchronous_oid_request_complete.md) handler, NDIS guarantees that the *FilterSynchronousOidRequestComplete* handler will be called if and only if the *FilterSynchronousOidRequest* handler returns NDIS_STATUS_SUCCESS.

The *FilterSynchronousOidRequest* handler can write any PVOID-sized value to _*CallContext_, and the same value will be returned to the filter driver’s *FilterSynchronousOidRequestComplete* handler when the OID request is completed. Filter driver can use this to carry state across the two handlers. Since the *FilterSynchronousOidRequestComplete* handler is only invoked if the *FilterSynchronousOidRequest* handler returns NDIS_STATUS_SUCCESS, there’s no reason to write a value to _*CallContext_ when returning any other code. Likewise, there’s no reason to write a value to _*CallContext_ if the filter driver does not provide a *FilterSynchronousOidRequestComplete* handler.

Filter drivers must not return NDIS_STATUS_PENDING from a *FilterSynchronousOidRequest* handler. Synchronous OID requests cannot be pended or cancelled.

Filter drivers are expected to return from their *FilterSynchronousOidRequest* handler quickly, without blocking, waiting, or sleeping. Synchronous OID requests are only used for low-latency operations, and filter drivers should strive to continue or complete them within several milliseconds.
NDIS does not serialize Synchronous OID requests against each other, against other OID requests, or against [*FilterPause*](nc-ndis-filter_pause.md). It is the responsibility of the filter driver to implement any needed synchronization.

NDIS does serialize Synchronous OID requests against [*FilterDetach*](nc-ndis-filter_detach.md): NDIS guarantees that no Synchronous OID requests will be active once *FilterDetach* is invoked.

Filter drivers must not call [**NdisAllocateCloneOidRequest**](nf-ndis-ndisallocatecloneoidrequest.md) or [**NdisCancelOidRequest**](nf-ndis-ndiscanceloidrequest.md) on a Synchronous OID request. Filter drivers must not call [**NdisFSynchronousOidRequest**](nf-ndis-ndisfsynchronousoidrequest.md) on an OID request that is received through a *FilterSynchronousOidRequest* handler.

If a filter driver raises the IRQL in its *FilterSynchronousOidRequest* handler, it must restore the IRQL to its initial level before returning from its *FilterSynchronousOidRequest* handler.

## -see-also

[*FilterSynchronousOidRequestComplete*](nf-ndis-filter_synchronous_oid_request_complete.md)

[**NdisFSynchronousOidRequest**](nf-ndis-ndisfsynchronousoidrequest.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/network/synchronous-oid-request-interface-in-ndis-6-80">Synchronous OID Request Interface in NDIS 6.80</a>
 

 

