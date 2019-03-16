---
UID: NF:ndis.NdisMPauseComplete
title: NdisMPauseComplete function (ndis.h)
description: A miniport driver must call the NdisMPauseComplete function to complete a pause operation if the driver returned NDIS_STATUS_PENDING from its MiniportPause function.
old-location: netvista\ndismpausecomplete.htm
tech.root: netvista
ms.assetid: 08a9dccf-53bc-4b96-a794-14ead08a7b0b
ms.date: 05/02/2018
ms.keywords: NdisMPauseComplete, NdisMPauseComplete function [Network Drivers Starting with Windows Vista], miniport_ndis_functions_ref_1e76f7bc-a042-4a7a-8dc6-0f4cc6f7617f.xml, ndis/NdisMPauseComplete, netvista.ndismpausecomplete
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
- NdisMPauseComplete
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisMPauseComplete function


## -description


A miniport driver must call the 
  <b>NdisMPauseComplete</b> function to complete a pause operation if the driver returned NDIS_STATUS_PENDING
  from its 
  <a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a> function.


## -parameters




### -param MiniportAdapterHandle [in]

The miniport adapter handle that NDIS passed to the 
     <i>MiniportAdapterHandle</i> parameter of 
     <a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>.


## -returns



None




## -remarks



NDIS calls a miniport driver's 
    <a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a> function to initiate a
    pause request for a miniport adapter. The miniport adapter remains in the 
    <i>Pausing</i> state until the pause operation is complete.

After a miniport driver completes all outstanding send requests and NDIS returns all the network data
    structures in outstanding receive indications to the driver, the driver calls 
    <b>NdisMPauseComplete</b> to complete the pending pause request. After the driver calls 
    <b>NdisMPauseComplete</b>, the miniport adapter is in the 
    <i>Paused</i> state.

NDIS calls the 
    <a href="https://msdn.microsoft.com/31a18040-2c66-4074-9ace-dd604b4bfe22">MiniportRestart</a> function to initiate a
    restart request for a miniport adapter that is paused.




## -see-also




<a href="https://msdn.microsoft.com/b146fa81-005b-4a6c-962d-4cb023ea790e">MiniportInitializeEx</a>



<a href="https://msdn.microsoft.com/047241a5-6f52-4a82-a334-8508f0de5e1a">MiniportPause</a>



<a href="https://msdn.microsoft.com/31a18040-2c66-4074-9ace-dd604b4bfe22">MiniportRestart</a>
 

 

