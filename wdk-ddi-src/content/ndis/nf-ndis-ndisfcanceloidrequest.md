---
UID: NF:ndis.NdisFCancelOidRequest
title: NdisFCancelOidRequest function (ndis.h)
description: Filter drivers call the NdisFCancelOidRequest function to cancel a previous request to the underlying drivers.
old-location: netvista\ndisfcanceloidrequest.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFCancelOidRequest function"]
ms.keywords: NdisFCancelOidRequest, NdisFCancelOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFCancelOidRequest, ndis_request_ref_17e19328-030e-4649-94c9-f7b0347e7ab2.xml, netvista.ndisfcanceloidrequest
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
 - NdisFCancelOidRequest
 - ndis/NdisFCancelOidRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFCancelOidRequest
---

# NdisFCancelOidRequest function


## -description

Filter drivers call the 
  <b>NdisFCancelOidRequest</b> function to cancel a previous request to the underlying drivers.

## -parameters

### -param NdisFilterHandle 

[in]
The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param RequestId 

[in]
A cancellation identifier for the request. This identifier specifies the 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.

## -remarks

Filter drivers call 
    <b>NdisFCancelOidRequest</b> to cancel a previously issued request. The request can be originated by the
    filter driver or by overlying drivers. The pointer passed at 
    <i>OidRequest</i> must be the same pointer that was passed in the call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelOidRequest</b> from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_oid_request">FilterCancelOidRequest</a> function
    to pass on the cancellation to underlying drivers.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_oid_request">FilterCancelOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfoidrequest">NdisFOidRequest</a>
