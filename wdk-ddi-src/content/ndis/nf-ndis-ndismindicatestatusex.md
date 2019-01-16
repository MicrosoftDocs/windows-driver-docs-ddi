---
UID: NF:ndis.NdisMIndicateStatusEx
title: NdisMIndicateStatusEx function
description: The NdisMIndicateStatusEx function reports a change in the status of a miniport adapter.
old-location: netvista\ndismindicatestatusex.htm
tech.root: netvista
ms.assetid: df857349-4ae1-470b-b41a-ff014f40b79b
ms.date: 05/02/2018
ms.keywords: NdisMIndicateStatusEx, NdisMIndicateStatusEx function [Network Drivers Starting with Windows Vista], ndis/NdisMIndicateStatusEx, ndis_status_ref_73b76336-b2c8-41f9-9d4f-12e5c5988a3d.xml, netvista.ndismindicatestatusex
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_StatusIndication_Function, NdisMIndicateStatusEx, WlanAssociation, WlanConnectionRoaming, WlanDisassociation, WlanTimedAssociation, WlanTimedConnectionRoaming, WlanTimedConnectRequest, WlanTimedLinkQuality, WlanTimedScan
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
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisMIndicateStatusEx
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMIndicateStatusEx function


## -description


The 
  <b>NdisMIndicateStatusEx</b> function reports a change in the status of a miniport adapter.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param StatusIndication [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## -returns



None




## -remarks



When a miniport driver calls 
    <b>NdisMIndicateStatusEx</b>, NDIS calls each bound protocol driver's 
    <a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a> function. This allows
    a bound protocol driver to log the change in status of an underlying miniport adapter or to take
    action.

A miniport driver can call 
    <b>NdisMIndicateStatusEx</b> after setting its registration attributes even if the driver is still in the
    context of the 
    <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a> function. The
    driver must not call 
    <b>NdisMIndicateStatusEx</b> after it returns from the 
    <a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a> function.




## -see-also




<a href="https://msdn.microsoft.com/b8d452b4-bef3-4991-87cf-fac15bedfde4">MiniportHaltEx</a>



<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff567373">NDIS_STATUS_INDICATION</a>



<a href="https://msdn.microsoft.com/5bc5a24f-5f28-4502-8776-b1cf15fd8283">ProtocolStatusEx</a>
 

 

