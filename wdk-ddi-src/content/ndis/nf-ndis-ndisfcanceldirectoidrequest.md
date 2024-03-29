---
UID: NF:ndis.NdisFCancelDirectOidRequest
title: NdisFCancelDirectOidRequest function (ndis.h)
description: Filter drivers call the NdisFCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndisfcanceldirectoidrequest.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisFCancelDirectOidRequest function"]
ms.keywords: NdisFCancelDirectOidRequest, NdisFCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFCancelDirectOidRequest, ndis_request_direct_ref_48dc16f9-1c11-41de-9c37-91abed86b06c.xml, netvista.ndisfcanceldirectoidrequest
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
 - NdisFCancelDirectOidRequest
 - ndis/NdisFCancelDirectOidRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisFCancelDirectOidRequest
---

# NdisFCancelDirectOidRequest function


## -description

Filter drivers call the 
  <b>NdisFCancelDirectOidRequest</b> function to cancel a previous direct OID request to the underlying
  drivers.

## -parameters

### -param NdisFilterHandle [in]


The NDIS handle that identifies this filter module. NDIS passed the handle to the filter driver in
     a call to the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.

### -param RequestId [in]


A cancellation identifier for the request. This identifier specifies the 
     <a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.

## -remarks

Filter drivers call 
    <b>NdisFCancelDirectOidRequest</b> to cancel a previously issued direct OID request. The request can be
    originated by the filter driver or by overlying drivers. The pointer that is passed at the 
    <i>OidRequest</i> parameter must be the same pointer that was passed in the call to the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelDirectOidRequest</b> from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_direct_oid_request">
    FilterCancelDirectOidRequest</a> function to pass on the cancellation to underlying drivers.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_cancel_direct_oid_request">
   FilterCancelDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/oidrequest/ns-oidrequest-ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a>
