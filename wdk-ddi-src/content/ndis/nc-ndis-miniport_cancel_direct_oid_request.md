---
UID: NC:ndis.MINIPORT_CANCEL_DIRECT_OID_REQUEST
title: MINIPORT_CANCEL_DIRECT_OID_REQUEST (ndis.h)
description: NDIS calls a miniport driver's MiniportCancelDirectOidRequest function to cancel a direct OID request.
old-location: netvista\miniportcanceldirectoidrequest.htm
tech.root: netvista
ms.assetid: 88639bb4-89f3-4e7f-9cce-ea541224572d
ms.date: 05/02/2018
keywords: ["MINIPORT_CANCEL_DIRECT_OID_REQUEST callback function"]
ms.keywords: MINIPORT_CANCEL_DIRECT_OID_REQUEST, MINIPORT_CANCEL_DIRECT_OID_REQUEST callback, MiniportCancelDirectOidRequest, MiniportCancelDirectOidRequest callback function [Network Drivers Starting with Windows Vista], ndis/MiniportCancelDirectOidRequest, ndis_request_direct_ref_d98875f6-2607-4d82-ac0f-615a33c0b11e.xml, netvista.miniportcanceldirectoidrequest
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
 - MINIPORT_CANCEL_DIRECT_OID_REQUEST
 - ndis/MINIPORT_CANCEL_DIRECT_OID_REQUEST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Ndis.h
api_name:
 - MiniportCancelDirectOidRequest
---

# MINIPORT_CANCEL_DIRECT_OID_REQUEST callback function


## -description

NDIS calls a miniport driver's 
   <i>MiniportCancelDirectOidRequest</i> function to cancel a direct OID request.
<div class="alert"><b>Note</b>  You must declare the function by using the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> type.
   For more information, see the following Examples section.</div><div> </div>

## -parameters

### -param MiniportAdapterContext 

[in]
A handle to a context area that the miniport driver allocated in its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function.
     The miniport driver uses this context area to maintain state information for a miniport adapter.

### -param RequestId 

[in]
A cancellation identifier for the request. This identifier specifies the direct OID requests that
     match this value in the 
     <b>RequestId</b> member of the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.

## -remarks

<i>MiniportCancelDirectOidRequest</i> is an optional function. A miniport driver registers this function
    if it handles direct OID requests. A driver specifies the 
    <i>MiniportCancelDirectOidRequest</i> entry point when it calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">
    NdisMRegisterMiniportDriver</a> function. A miniport driver that registers the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">
    MiniportDirectOidRequest</a> function must also register 
    <i>MiniportCancelDirectOidRequest</i>.

When NDIS calls 
    <i>MiniportCancelDirectOidRequest</i>, the miniport driver should attempt to call 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismdirectoidrequestcomplete">
    NdisMDirectOidRequestComplete</a> function as soon as possible.

NDIS calls 
    <i>MiniportCancelDirectOidRequest</i> when the originator of the request cancels the request. For direct
    OID requests, NDIS does not call 
    <i>MiniportCancelDirectOidRequest</i> if the time-out expires. (The time-out is specified at the 
    <b>Timeout</b> member of each 
    <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.)

If the request processing is still not complete in a miniport driver, the driver calls the 
    <b>NdisMDirectOidRequestComplete</b> function with the status set to NDIS_STATUS_REQUEST_ABORTED.

If the request processing is still not complete in an intermediate driver and the request was
    propagated to an underlying driver, the intermediate driver calls the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceldirectoidrequest">
    NdisCancelDirectOidRequest</a> function with the 
    <i>OidRequest</i> parameter set to the value that it sent to the underlying driver.

NDIS calls 
    <i>MiniportCancelDirectOidRequest</i> at IRQL <= DISPATCH_LEVEL.

<h3><a id="Examples"></a><a id="examples"></a><a id="EXAMPLES"></a>Examples</h3>
To define a <i>MiniportCancelDirectOidRequest</i> function, you must first provide a function declaration that identifies the type of function you're defining. Windows provides a set of function types for drivers. Declaring a function using the function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>MiniportCancelDirectOidRequest</i> function that is named "MyCancelDirectOidRequest", use the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> type as shown in this code example:


```
MINIPORT_CANCEL_DIRECT_OID_REQUEST MyCancelDirectOidRequest;
```

Then, implement your function as follows:


```
_Use_decl_annotations_
VOID
 MyCancelDirectOidRequest(
    NDIS_HANDLE  MiniportAdapterContext,
    PVOID  RequestId
    )
  {...}
```

The <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> function type is defined in the Ndis.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition.  The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the <b>MINIPORT_CANCEL_DIRECT_OID_REQUEST</b> function type in the header file are used.  For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-ndis-drivers">Declaring Functions by Using Function Role Types for NDIS Drivers</a>.

For information about  _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">MiniportDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndiscanceldirectoidrequest">NdisCancelDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismdirectoidrequestcomplete">
   NdisMDirectOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismregisterminiportdriver">NdisMRegisterMiniportDriver</a>