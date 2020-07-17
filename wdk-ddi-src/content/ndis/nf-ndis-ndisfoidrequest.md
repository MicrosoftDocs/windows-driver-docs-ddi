---
UID: NF:ndis.NdisFOidRequest
title: NdisFOidRequest function (ndis.h)
description: Filter drivers call the NdisFOidRequest function to forward an OID request to underlying drivers or to originate such a request.
old-location: netvista\ndisfoidrequest.htm
tech.root: netvista
ms.assetid: 8434bf2c-9c9a-49a1-bf88-b67b1eec721c
ms.date: 05/02/2018
keywords: ["NdisFOidRequest function"]
ms.keywords: NdisFOidRequest, NdisFOidRequest function [Network Drivers Starting with Windows Vista], ndis/NdisFOidRequest, ndis_request_ref_b5034fc8-9122-4c87-b690-a6989c1592c1.xml, netvista.ndisfoidrequest
f1_keywords:
 - "ndis/NdisFOidRequest"
 - "NdisFOidRequest"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisFOidRequest
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisFOidRequest function


## -description


Filter drivers call the 
  <b>NdisFOidRequest</b> function to forward an OID request to underlying drivers or to originate such a
  request.


## -parameters




### -param NdisFilterHandle [in]

An NDIS handle that identifies a filter module. NDIS passed the handle to the filter driver in a
     call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a> function.


### -param OidRequest [in]

A pointer to an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure that specifies
     the operation requested with a given OID_<i>XXX</i> code. The structure can specify a query, set, or method request. For more information about
     OIDs, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/_netvista/">NDIS OIDs</a>.


## -returns



See the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function.




## -remarks



Filter drivers can originate OID requests to underlying drivers by calling 
    <b>NdisFOidRequest</b>.

Filter drivers can also filter OID requests that are originated by overlying drivers. NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a> function to process
    each such request.

If 
    <b>NdisFOidRequest</b> returns <b>NDIS_STATUS_PENDING</b>, NDIS calls the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request_complete">FilterOidRequestComplete</a> function after the underlying drivers complete the OID request.

If 
    <b>NdisFOidRequest</b> returns <b>NDIS_STATUS_SUCCESS</b>, it returns the results of a query request in the
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure at the 
    <i>OidRequest</i> parameter.

<b>NdisFOidRequest</b> can return <b>NDIS_STATUS_INVALID_PARAMETER</b> if the filter driver passes invalid values
    for the 
    <b>Type</b> and 
    <b>Size</b> fields in the 
    <b>Header</b> field of the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure.

A driver can call 
    <b>NdisFOidRequest</b> when it is in the 
    <i>Restarting</i>, 
    <i>Running</i>, 
    <i>Pausing</i>, or 
    <i>Paused</i> state.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_attach">FilterAttach</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request">FilterOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_oid_request_complete">FilterOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a>
 

 

