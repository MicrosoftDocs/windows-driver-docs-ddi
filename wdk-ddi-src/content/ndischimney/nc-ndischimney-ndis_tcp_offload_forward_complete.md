---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_FORWARD_COMPLETE
title: NDIS_TCP_OFFLOAD_FORWARD_COMPLETE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadForwardComplete function to complete one or more forward requests that were made to the MiniportTcpOffloadForward function of the offload target.
old-location: netvista\ndistcpoffloadforwardcomplete.htm
old-project: netvista
ms.assetid: 080949ab-8a27-4d13-992e-597210d4882c
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: NDIS_TCP_OFFLOAD_FORWARD_COMPLETE, NdisTcpOffloadForwardComplete, NdisTcpOffloadForwardComplete callback function [Network Drivers Starting with Windows Vista], ndischimney/NdisTcpOffloadForwardComplete, netvista.ndistcpoffloadforwardcomplete, tcp_chim_ndis_func_a6483879-a4ae-49e0-859f-51a66070566d.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
req.lib: 
req.dll: 
req.irql: Any level
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	ndischimney.h
api_name:
-	NdisTcpOffloadForwardComplete
product:
- Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NDIS_TCP_OFFLOAD_FORWARD_COMPLETE callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadForwardComplete</b> function to complete one or more forward requests that were made to the
  
  <a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">
  MiniportTcpOffloadForward</a> function of the offload target.


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <a href="https://msdn.microsoft.com/bed68aa8-499d-41fd-997b-a46316913cc8">
     NdisMRegisterMiniportDriver</a> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The offload
     target obtained these structures in one or more calls to its 
     <a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">
     MiniportTcpOffloadForward</a> function.


## -returns



None




## -remarks



To improve system performance, an offload target can create a linked list that contains 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structures from multiple
    calls to the 
    <a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">
    MiniportTcpOffloadForward</a> function. The offload target can then pass such a linked list in a single
    call to the 
    <b>NdisTcpOffloadForwardComplete</b> function.

An offload target must write one of the following status values to each NET_BUFFER_LIST structure that
    it passes to the 
    <b>NdisTcpOffloadForwardComplete</b> function:






## -see-also




<a href="https://msdn.microsoft.com/e5702476-60a3-4bfc-b959-198e98f0f9ba">MiniportTcpOffloadForward</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff563654">NdisMRegisterMiniportDriver</a>
 

 

