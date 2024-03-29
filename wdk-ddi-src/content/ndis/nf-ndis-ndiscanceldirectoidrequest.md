---
UID: NF:ndis.NdisCancelDirectOidRequest
title: NdisCancelDirectOidRequest function (ndis.h)
description: Protocol drivers call the NdisCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndiscanceldirectoidrequest.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisCancelDirectOidRequest function"]
ms.keywords: NdisCancelDirectOidRequest, NdisCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisCancelDirectOidRequest, ndis_request_direct_ref_71cb0f66-b7f7-49b5-b006-ca50eff45bcb.xml, netvista.ndiscanceldirectoidrequest
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
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
req.lib: Ndis.lib
req.dll: 
req.irql: <= DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - NdisCancelDirectOidRequest
 - ndis/NdisCancelDirectOidRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisCancelDirectOidRequest
---

# NdisCancelDirectOidRequest function


## -description

Protocol drivers call the 
  <b>NdisCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.

## -parameters

### -param NdisBindingHandle [in]


The handle that the 
     <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a> function returned
     that identifies the target miniport adapter on the binding.

### -param RequestId [in]


A cancellation identifier for the request. This identifier specifies the 
     <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.

## -remarks

Protocol drivers call the 
    <b>NdisCancelDirectOidRequest</b> function to cancel a previously issued direct OID request. The request
    ID that is passed at the 
    <i>RequestId</i> parameter must match the request ID in the 
    <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structure that was passed
    in the call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdirectoidrequest">NdisDirectOidRequest</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisdirectoidrequest">NdisDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisopenadapterex">NdisOpenAdapterEx</a>
