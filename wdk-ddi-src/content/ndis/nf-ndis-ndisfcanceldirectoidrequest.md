---
UID: NF:ndis.NdisFCancelDirectOidRequest
title: NdisFCancelDirectOidRequest function (ndis.h)
description: Filter drivers call the NdisFCancelDirectOidRequest function to cancel a previous direct OID request to the underlying drivers.
old-location: netvista\ndisfcanceldirectoidrequest.htm
tech.root: netvista
ms.assetid: 05cbeca1-7420-41c6-8868-980b265523db
ms.date: 05/02/2018
ms.keywords: NdisFCancelDirectOidRequest, NdisFCancelDirectOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFCancelDirectOidRequest, ndis_request_direct_ref_48dc16f9-1c11-41de-9c37-91abed86b06c.xml, netvista.ndisfcanceldirectoidrequest
ms.topic: function
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
req.irql: "<= DISPATCH_LEVEL"
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
product:
- Windows
targetos: Windows
req.typenames: 
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
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param RequestId [in]

A cancellation identifier for the request. This identifier specifies the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structures that are being
     canceled.


## -returns



None




## -remarks



Filter drivers call 
    <b>NdisFCancelDirectOidRequest</b> to cancel a previously issued direct OID request. The request can be
    originated by the filter driver or by overlying drivers. The pointer that is passed at the 
    <i>OidRequest</i> parameter must be the same pointer that was passed in the call to the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a> function.

The filter driver can call 
    <b>NdisFCancelDirectOidRequest</b> from the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_cancel_direct_oid_request">
    FilterCancelDirectOidRequest</a> function to pass on the cancellation to underlying drivers.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_cancel_direct_oid_request">
   FilterCancelDirectOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisfdirectoidrequest">NdisFDirectOidRequest</a>
 

 

