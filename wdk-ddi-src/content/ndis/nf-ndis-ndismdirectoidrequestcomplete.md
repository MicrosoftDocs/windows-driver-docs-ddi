---
UID: NF:ndis.NdisMDirectOidRequestComplete
title: NdisMDirectOidRequestComplete function (ndis.h)
description: Miniport drivers call the NdisMDirectOidRequestComplete function to return the final status of a direct OID request for which the driver's MiniportDirectOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndismdirectoidrequestcomplete.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["NdisMDirectOidRequestComplete function"]
ms.keywords: NdisMDirectOidRequestComplete, NdisMDirectOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMDirectOidRequestComplete, ndis_request_direct_ref_5f09825b-962f-41a9-b25d-e21c20e23249.xml, netvista.ndismdirectoidrequestcomplete
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
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
 - NdisMDirectOidRequestComplete
 - ndis/NdisMDirectOidRequestComplete
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMDirectOidRequestComplete
---

# NdisMDirectOidRequestComplete function


## -description

Miniport drivers call the 
  <b>NdisMDirectOidRequestComplete</b> function to return the final status of a direct OID request for which
  the driver's 
  <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">
  MiniportDirectOidRequest</a> function returned NDIS_STATUS_PENDING.

## -parameters

### -param MiniportAdapterHandle 

[in]
A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param OidRequest 

[in]
A pointer to a buffer that is formatted as an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <i>MiniportDirectOidRequest</i> function.

### -param Status 

[in]
The final status of the request operation: NDIS_STATUS_SUCCESS, NDIS_STATUS_REQUEST_ABORTED, or
     any driver-determined NDIS_STATUS_<i>Xxx</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">
     MiniportDirectOidRequest</a>.

## -remarks

A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">
    MiniportDirectOidRequest</a> function must call 
    <b>NdisMDirectOidRequestComplete</b> after the miniport driver has finished the request operation.

If an overlying driver originated the direct OID request, NDIS calls the request complete function
    (see 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_direct_oid_request_complete">
    ProtocolDirectOidRequestComplete</a> and 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request_complete">
    FilterDirectOidRequestComplete</a>) of the overlying that originated the request.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-filter_direct_oid_request_complete">
   FilterDirectOidRequestComplete</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_direct_oid_request">MiniportDirectOidRequest</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_direct_oid_request_complete">
   ProtocolDirectOidRequestComplete</a>
