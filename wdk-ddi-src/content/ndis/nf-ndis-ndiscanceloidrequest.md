---
UID: NF:ndis.NdisCancelOidRequest
title: NdisCancelOidRequest function (ndis.h)
description: Protocol drivers call the NdisCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndiscanceloidrequest.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisCancelOidRequest function"]
ms.keywords: NdisCancelOidRequest, NdisCancelOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisCancelOidRequest, ndis_request_ref_5f7f8a9a-f773-4ca8-aba3-21fe74431e0c.xml, netvista.ndiscanceloidrequest
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_OID_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisCancelOidRequest
 - ndis/NdisCancelOidRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisCancelOidRequest
---

# NdisCancelOidRequest function


## -description

Protocol drivers call the 
  <b>NdisCancelOidRequest</b> function to cancel a previous request to the underlying drivers.

## -parameters

### -param NdisBindingHandle [in]


The handle returned by the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function that
     identifies the target adapter on the binding.

### -param RequestId [in]


A cancellation identifier for the request. This identifier specifies the 
     <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.

## -remarks

Protocol drivers call this function to cancel a previously issued request. The request ID that is
    passed at the 
    <i>RequestId</i> parameter must match the request ID in the 
    <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structure that was passed
    in the call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>
