---
UID: NF:ndis.NdisIfDeregisterInterface
title: NdisIfDeregisterInterface function (ndis.h)
description: The NdisIfDeregisterInterface function deregisters an NDIS network interface that was previously registered by a call to the NdisIfRegisterInterface function.
old-location: netvista\ndisifderegisterinterface.htm
tech.root: netvista
ms.assetid: 696d0870-966e-44ac-859e-d530dd6c76b8
ms.date: 05/02/2018
keywords: ["NdisIfDeregisterInterface function"]
ms.keywords: NdisIfDeregisterInterface, NdisIfDeregisterInterface function [Network Drivers Starting with Windows Vista], ndis/NdisIfDeregisterInterface, net_if_functions_ref_dc1bdf3d-3cca-4d4a-b0f9-4bdef32bcdb0.xml, netvista.ndisifderegisterinterface
f1_keywords:
 - "ndis/NdisIfDeregisterInterface"
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Desktop
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: Irql_Interfaces_Function
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Ndis.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- ndis.lib
- ndis.dll
api_name:
- NdisIfDeregisterInterface
product:
- Windows
targetos: Windows
req.typenames: 
---

# NdisIfDeregisterInterface function


## -description


The 
  <b>NdisIfDeregisterInterface</b> function deregisters an NDIS network interface that was previously
  registered by a call to the 
  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">
  NdisIfRegisterInterface</a> function.


## -parameters




### -param ifIndex

An index that identifies the network interface to deregister. The interface provider obtained this
     index from a previous call to the 
     <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">
     NdisIfRegisterInterface</a> function.

## -remarks



NDIS interface providers call the 
    <b>NdisIfDeregisterInterface</b> function to deregister a network interface and to indicate that the
    interface should be removed from the list of known interfaces on the computer.

An interface provider calls the 
    <b>NdisIfDeregisterInterface</b> function, for example, because the interface has been uninstalled.
    Interface providers do not call 
    <b>NdisIfDeregisterInterface</b> to indicate that an interface has changed state.

<b>NdisIfDeregisterInterface</b> releases the interface index, so NDIS can reassign the index to another
    interface that is registered later. Do not confuse the interface index with the 
    <a href="https://docs.microsoft.com/windows/desktop/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a> index, which persists after a computer
    restarts.




## -see-also




<a href="https://docs.microsoft.com/windows/desktop/api/ifdef/ns-ifdef-net_luid_lh">NET_LUID</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ndis/nf-ndis-ndisifregisterinterface">NdisIfRegisterInterface</a>
 

 

