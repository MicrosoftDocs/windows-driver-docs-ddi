---
UID: NF:ndis.NdisMIndicateStatusEx
title: NdisMIndicateStatusEx function
author: windows-driver-content
description: The NdisMIndicateStatusEx function reports a change in the status of a miniport adapter.
old-location: netvista\ndismindicatestatusex.htm
old-project: netvista
ms.assetid: df857349-4ae1-470b-b41a-ff014f40b79b
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis_status_ref_73b76336-b2c8-41f9-9d4f-12e5c5988a3d.xml, netvista.ndismindicatestatusex, NdisMIndicateStatusEx, NdisMIndicateStatusEx function [Network Drivers Starting with Windows Vista], ndis/NdisMIndicateStatusEx
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	ndis.lib
-	ndis.dll
apiname:
-	NdisMIndicateStatusEx
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMIndicateStatusEx function


## -description


The 
  <b>NdisMIndicateStatusEx</b> function reports a change in the status of a miniport adapter.


## -syntax


````
VOID NdisMIndicateStatusEx(
  _In_ NDIS_HANDLE             MiniportAdapterHandle,
  _In_ PNDIS_STATUS_INDICATION StatusIndication
);
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed at the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.


### -param StatusIndication [in]

A pointer to an 
     <a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a> structure
     that contains the status information.


## -returns


None



## -remarks


When a miniport driver calls 
    <b>NdisMIndicateStatusEx</b>, NDIS calls each bound protocol driver's 
    <a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a> function. This allows
    a bound protocol driver to log the change in status of an underlying miniport adapter or to take
    action.

A miniport driver can call 
    <b>NdisMIndicateStatusEx</b> after setting its registration attributes even if the driver is still in the
    context of the 
    <a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a> function. The
    driver must not call 
    <b>NdisMIndicateStatusEx</b> after it returns from the 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function.



## -see-also

<a href="..\ndis\nc-ndis-protocol_status_ex.md">ProtocolStatusEx</a>

<a href="..\ndis\ns-ndis-_ndis_status_indication.md">NDIS_STATUS_INDICATION</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMIndicateStatusEx function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

