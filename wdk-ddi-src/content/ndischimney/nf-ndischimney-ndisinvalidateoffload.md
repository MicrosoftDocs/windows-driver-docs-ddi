---
UID: NF:ndischimney.NdisInvalidateOffload
title: NdisInvalidateOffload function
author: windows-driver-content
description: A protocol or intermediate driver calls the NdisInvalidateOffload function to invalidate previously offloaded TCP chimney state objects.
old-location: netvista\ndisinvalidateoffload.htm
old-project: netvista
ms.assetid: d9cb2724-cf14-4814-8a19-1237e0862b1a
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NdisInvalidateOffload, NdisInvalidateOffload function [Network Drivers Starting with Windows Vista], ndischimney/NdisInvalidateOffload, netvista.ndisinvalidateoffload, tcp_chim_ndis_func_f9049fdc-87ff-467c-9427-d42876e16aa3.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: ndischimney.h
req.include-header: Ndischimney.h
req.target-type: Universal
req.target-min-winverclnt: 
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	ndis.lib
-	ndis.dll
api_name:
-	NdisInvalidateOffload
product:
- Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NdisInvalidateOffload function


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

A protocol or intermediate driver calls the 
  <b>NdisInvalidateOffload</b> function to invalidate previously offloaded TCP chimney state objects.


## -parameters




### -param NdisBindingHandle [in]

The handle that NDIS provided at the 
     <i>NdisBindingHandle</i> parameter of 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>. This handle
     identifies the binding between the caller and the underlying intermediate driver or offload
     target.


### -param OffloadBlockList [in]

A pointer to an 
     <a href="https://msdn.microsoft.com/64febd55-1ab8-4e2e-b738-340167866333">
     NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a> structure that can be a stand-alone structure or the root of a
     linked list of such structures. These structures identify the state objects that are being
     invalidated.


## -returns



None




## -remarks



An intermediate driver calls the 
    <b>NdisInvalidateOffload</b> function to propagate an invalidate offload operation that was initiated by
    the host stack. For more information, see 
    <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/ff563771">Propagating
    State-Manipulation Operations</a>.

From the 
    <a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a> structure that was passed to its 
    <a href="https://msdn.microsoft.com/58226149-daea-40aa-afb6-13ce615434b3">
    MiniportInvalidateOffload</a> function, the intermediate driver constructs an
    NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure. For more information, see 
    <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/network/reusing-an-ndis-miniport-offload-block-list-structure">Reusing an
    NDIS_MINIPORT_OFFLOAD_BLOCK_LIST Structure</a>. The intermediate driver passes a pointer (the 
    <i>OffloadBlockList</i> parameter) to this NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST structure when calling the 
    <b>NdisInvalidateOffload</b> function.




## -see-also




<a href="https://msdn.microsoft.com/58226149-daea-40aa-afb6-13ce615434b3">MiniportInvalidateOffload</a>



<a href="https://msdn.microsoft.com/ebc98e65-5d11-4c3d-aea1-dfad1434c093">
   NDIS_MINIPORT_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/64febd55-1ab8-4e2e-b738-340167866333">
   NDIS_PROTOCOL_OFFLOAD_BLOCK_LIST</a>



<a href="https://msdn.microsoft.com/fd14e983-ea4b-41f2-973d-88b114306e75">
   NdisMInvalidateOffloadComplete</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563715">NdisOpenAdapterEx</a>



<a href="https://msdn.microsoft.com/6d2c71d0-9686-4eb5-9715-27de3dc8b390">
   ProtocolInvalidateOffloadComplete</a>
 

 

