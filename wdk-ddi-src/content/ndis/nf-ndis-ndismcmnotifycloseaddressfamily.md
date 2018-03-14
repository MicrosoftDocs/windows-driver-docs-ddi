---
UID: NF:ndis.NdisMCmNotifyCloseAddressFamily
title: NdisMCmNotifyCloseAddressFamily macro
author: windows-driver-content
description: The NdisMCmNotifyCloseAddressFamily function notifies NDIS that a specified address family (AF) that is associated with a miniport call manager (MCM) should be closed and NDIS should notify any affected CoNDIS clients.
old-location: netvista\ndismcmnotifycloseaddressfamily.htm
old-project: netvista
ms.assetid: 47b0b1da-e29b-45cc-921b-69d630670b44
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: NdisMCmNotifyCloseAddressFamily, NdisMCmNotifyCloseAddressFamily macro [Network Drivers Starting with Windows Vista], condis_mcm_ref_448486f3-1eeb-4f45-b764-6fd4ab06b63e.xml, ndis/NdisMCmNotifyCloseAddressFamily, netvista.ndismcmnotifycloseaddressfamily
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_MCM_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NdisMCmNotifyCloseAddressFamily
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMCmNotifyCloseAddressFamily macro


## -description


The 
  <b>NdisMCmNotifyCloseAddressFamily</b> function notifies NDIS that a specified address family (AF) that is
  associated with a miniport call manager (MCM) should be closed and NDIS should notify any affected CoNDIS
  clients.


## -syntax


````
NDIS_STATUS NdisMCmNotifyCloseAddressFamily(
  [in] NDIS_HANDLE NdisAfHandle
);
````


## -parameters




### -param _AH_

TBD






#### - NdisAfHandle [in]

A handle that identifies the AF that NDIS should close. NDIS supplied this handle to the MCM's 
     <a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a> function.


## -remarks



MCMs, which register as NDIS miniport drivers by calling the 
    <a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">
    NdisMRegisterMiniportDriver</a> function, can call the 
    <b>NdisMCmNotifyCloseAddressFamily</b> function. Stand-alone call managers instead call the 
    <a href="..\ndis\nf-ndis-ndiscmnotifycloseaddressfamily.md">
    NdisCmNotifyCloseAddressFamily</a> function.

To close an AF for a miniport adapter, the MCM should call 
    <b>NdisMCmNotifyCloseAddressFamily</b> from its 
    <a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a> function. NDIS
    subsequently calls the 
    <a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">
    ProtocolClNotifyCloseAf</a> function of the client that has the specified AF open.

If 
    <b>NdisMCmNotifyCloseAddressFamily</b> returns NDIS_STATUS_PENDING, NDIS calls the MCM's 
    <a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
    ProtocolCmNotifyCloseAfComplete</a> function after the client completes the AF close operation.




## -see-also

<a href="..\ndis\nf-ndis-ndiscmnotifycloseaddressfamily.md">
   NdisCmNotifyCloseAddressFamily</a>



<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>



<a href="..\ndis\nc-ndis-miniport_halt.md">MiniportHaltEx</a>



<a href="..\ndis\nc-ndis-protocol_cm_open_af.md">ProtocolCmOpenAf</a>



<a href="..\ndis\nc-ndis-protocol_cl_notify_close_af.md">ProtocolClNotifyCloseAf</a>



<a href="..\ndis\nc-ndis-protocol_cm_notify_close_af_complete.md">
   ProtocolCmNotifyCloseAfComplete</a>



 

 


