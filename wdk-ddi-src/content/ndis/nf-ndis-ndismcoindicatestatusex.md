---
UID: NF:ndis.NdisMCoIndicateStatusEx
title: NdisMCoIndicateStatusEx function (ndis.h)
description: The NdisMCoIndicateStatusEx function reports a change in the status of a CoNDIS miniport adapter.
old-location: netvista\ndismcoindicatestatusex.htm
tech.root: netvista
ms.assetid: e6d5bd94-d9cb-462f-84e4-bf9d70961e95
ms.date: 05/02/2018
keywords: ["NdisMCoIndicateStatusEx function"]
ms.keywords: NdisMCoIndicateStatusEx, NdisMCoIndicateStatusEx function [Network Drivers Starting with Windows Vista], condis_status_ref_1a0c27e2-e728-4b1d-8e45-9305869d3bfc.xml, ndis/NdisMCoIndicateStatusEx, netvista.ndismcoindicatestatusex
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCO_Function
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
 - NdisMCoIndicateStatusEx
 - ndis/NdisMCoIndicateStatusEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - ndis.lib
 - ndis.dll
api_name:
 - NdisMCoIndicateStatusEx
---

# NdisMCoIndicateStatusEx function


## -description

The 
  <b>NdisMCoIndicateStatusEx</b> function reports a change in the status of a CoNDIS miniport adapter.

## -parameters

### -param MiniportAdapterHandle 

[in]
The miniport adapter handle that NDIS passed at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">
     MiniportInitializeEx</a> function.

### -param NdisVcHandle 

[in, optional]
A handle that identifies the virtual connection (VC). The miniport driver obtained this handle as
     an input parameter to its 
     <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a> function, either
     when a client set up an outgoing call or when the call manager created a VC for a client-registered
     service access point (SAP). The call manager created the VC to indicate an incoming-call notification.
     To send the status indication to all protocol bindings, set this parameter to <b>NULL</b>.

### -param StatusIndication 

[in]
A pointer to an 
     <a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.

## -remarks

When a miniport driver calls 
    <b>NdisMCoIndicateStatusEx</b> with a <b>NULL</b> VC handle for the 
    <i>NdisVcHandle</i> parameter, NDIS forwards the status-change notification to all of the bound protocol
    drivers by calling each bound protocol driver's 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_status_ex">ProtocolCoStatusEx</a> function. A call
    to 
    <b>NdisMCoIndicateStatusEx</b> with a non-<b>NULL</b> VC handle restricts the status notification to clients or
    call managers that the miniport driver shares this VC handle with.

A miniport driver can call 
    <b>NdisMCoIndicateStatusEx</b> after setting its registration attributes, by calling the 
    <a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">
    NdisMSetMiniportAttributes</a> function from its 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a> function,
    even if the driver is still in the context of the 
    <i>MiniportInitializeEx</i> function. The driver must not call 
    <b>NdisMCoIndicateStatusEx</b> after it returns from the 
    <a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_co_create_vc">MiniportCoCreateVc</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_halt">MiniportHaltEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-miniport_initialize">MiniportInitializeEx</a>



<a href="/windows-hardware/drivers/ddi/ndis/ns-ndis-_ndis_status_indication">NDIS_STATUS_INDICATION</a>



<a href="/windows-hardware/drivers/ddi/ndis/nf-ndis-ndismsetminiportattributes">NdisMSetMiniportAttributes</a>



<a href="/windows-hardware/drivers/ddi/ndis/nc-ndis-protocol_co_status_ex">ProtocolCoStatusEx</a>