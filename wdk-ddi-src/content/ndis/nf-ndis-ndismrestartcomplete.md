---
UID: NF:ndis.NdisMRestartComplete
title: NdisMRestartComplete function (ndis.h)
description: A miniport driver must call the NdisMRestartComplete function to complete a restart operation if the driver returned NDIS_STATUS_PENDING from its MiniportRestart function.
old-location: netvista\ndismrestartcomplete.htm
tech.root: netvista
ms.assetid: f43137ed-2ea3-4b7c-8d61-bda76bcb5f34
ms.date: 05/02/2018
ms.keywords: NdisMRestartComplete, NdisMRestartComplete function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_ee1a63ca-c2c4-422b-8c8a-163785c58802.xml, ndis/NdisMRestartComplete, netvista.ndismrestartcomplete
ms.topic: function
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Universal
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Miniport_Driver_Function
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
- NdisMRestartComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMRestartComplete function


## -description


A miniport driver must call the 
  <b>NdisMRestartComplete</b> function to complete a restart operation if the driver returned
  NDIS_STATUS_PENDING from its 
  <a href="https://msdn.microsoft.com/31a18040-2c66-4074-9ace-dd604b4bfe22">MiniportRestart</a> function.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of the 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">
     MiniportInitializeEx</a> function.


### -param Status [in]

The final status of the restart operation. The following status values are supported:
     





#### NDIS_STATUS_SUCCESS

The driver successfully restarted the flow of network data through the miniport adapter.



#### NDIS_STATUS_RESOURCES

The restart failed because of insufficient resources.



#### NDIS_STATUS_FAILURE

The driver indicates NDIS_STATUS_FAILURE if none of the preceding values applies. The driver
       should call the 
       <a href="https://msdn.microsoft.com/library/windows/hardware/ff564663">NdisWriteErrorLogEntry</a> function
       with parameters that specify the reason for the failure.


## -returns



None




## -remarks



The miniport adapter specified at 
    <i>MiniportAdapterHandle</i> enters the 
    <i>Restarting</i> state when NDIS calls the 
    <a href="https://msdn.microsoft.com/31a18040-2c66-4074-9ace-dd604b4bfe22">MiniportRestart</a> function.

After the miniport driver successfully restarts the send and receive operations for the miniport
    adapter, the driver must complete the pending restart operation. The pending restart operation is
    complete after the driver calls 
    <b>NdisMRestartComplete</b>. The miniport adapter is in the 
    <i>Running</i> state after the restart operation is complete.

A miniport driver can resume indicating received packets immediately after NDIS calls 
    <a href="https://msdn.microsoft.com/31a18040-2c66-4074-9ace-dd604b4bfe22">MiniportRestart</a> and before the driver calls 
    <b>NdisMRestartComplete</b>. The driver should be ready to accept send requests after it completes the
    restart request.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/31a18040-2c66-4074-9ace-dd604b4bfe22">MiniportRestart</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564663">NdisWriteErrorLogEntry</a>
 

 

