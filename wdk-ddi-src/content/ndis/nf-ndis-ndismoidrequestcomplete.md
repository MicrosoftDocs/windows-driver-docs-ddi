---
UID: NF:ndis.NdisMOidRequestComplete
title: NdisMOidRequestComplete function (ndis.h)
description: Miniport drivers call the NdisMOidRequestComplete function to return the final status of an OID request for which the driver's MiniportOidRequest function returned NDIS_STATUS_PENDING.
old-location: netvista\ndismoidrequestcomplete.htm
tech.root: netvista
ms.assetid: 30d060d0-05a3-42b5-b5ff-2f2b12873ca9
ms.date: 05/02/2018
ms.keywords: NdisMOidRequestComplete, NdisMOidRequestComplete function [Network Drivers Starting with Windows Vista], ndis/NdisMOidRequestComplete, ndis_request_ref_b5524732-acaf-4d0d-a261-3f8a8b739ecc.xml, netvista.ndismoidrequestcomplete
ms.topic: function
f1_keywords:
 - "ndis/NdisMOidRequestComplete"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: DoubleComplete, DoubleCompleteWorkItem, Irql_OID_Function, NdisMNetPnPEventInOIDRequest, NdisOidComplete, NdisOidDoubleComplete, NdisOidDoubleRequest, NdisTimedOidComplete, WlanAssociation, WlanDisassociation, WlanTimedConnectRequest, WlanTimedLinkQuality, WlanTimedScan
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
- NdisMOidRequestComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMOidRequestComplete function


## -description


Miniport drivers call the 
  <b>NdisMOidRequestComplete</b> function to return the final status of an OID request for which the driver's 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function returned
  NDIS_STATUS_PENDING.


## -parameters




### -param MiniportAdapterHandle [in]

A miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.


### -param OidRequest [in]

A pointer to a buffer that is formatted as an 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a> structure. The miniport
     driver obtained this pointer as an input parameter to its 
     <i>MiniportOidRequest</i> function.


### -param Status [in]

The final status of the request operation, either NDIS_STATUS_SUCCESS,
     NDIS_STATUS_REQUEST_ABORTED, or any driver-determined NDIS_STATUS_<i>XXX</i><u>except</u> NDIS_STATUS_PENDING. For more information about OID status values, see 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a>.


## -returns



None




## -remarks



A miniport driver that returns NDIS_STATUS_PENDING from its 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a> function must
    call 
    <b>NdisMOidRequestComplete</b> after the miniport driver has finished the request operation.

A call to 
    <b>NdisMOidRequestComplete</b> causes a call to the request complete function (see 
    <a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff563254(v=vs.85)">ProtocolRequestComplete</a>, 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_oid_request_complete">ProtocolOidRequestComplete</a>,    
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_oid_request_complete">FilterOidRequestComplete</a>) of
    the overlying driver that called the 
    <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a> function.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-filter_oid_request_complete">FilterOidRequestComplete</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-miniport_oid_request">MiniportOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/ns-ndis-_ndis_oid_request">NDIS_OID_REQUEST</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nf-ndis-ndisoidrequest">NdisOidRequest</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ndis/nc-ndis-protocol_oid_request_complete">ProtocolOidRequestComplete</a>



<a href="https://docs.microsoft.com/previous-versions/windows/hardware/network/ff563254(v=vs.85)">ProtocolRequestComplete</a>
 

 

