---
UID: NC:ndischimney.NDIS_TCP_OFFLOAD_FORWARD_COMPLETE
title: NDIS_TCP_OFFLOAD_FORWARD_COMPLETE
author: windows-driver-content
description: An offload target calls the NdisTcpOffloadForwardComplete function to complete one or more forward requests that were made to the MiniportTcpOffloadForward function of the offload target.
old-location: netvista\ndistcpoffloadforwardcomplete.htm
old-project: netvista
ms.assetid: 080949ab-8a27-4d13-992e-597210d4882c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndistcpoffloadforwardcomplete, NdisTcpOffloadForwardComplete callback function [Network Drivers Starting with Windows Vista], NdisTcpOffloadForwardComplete, NDIS_TCP_OFFLOAD_FORWARD_COMPLETE, NDIS_TCP_OFFLOAD_FORWARD_COMPLETE, ndischimney/NdisTcpOffloadForwardComplete, tcp_chim_ndis_func_a6483879-a4ae-49e0-859f-51a66070566d.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	ndischimney.h
apiname:
-	NdisTcpOffloadForwardComplete
product: Windows
targetos: Windows
req.typenames: PD_BUFFER_VIRTUAL_SUBNET_INFO
---

# NDIS_TCP_OFFLOAD_FORWARD_COMPLETE callback


## -description


<p class="CCE_Message">[The TCP chimney offload feature is deprecated and should not be used.]

An offload target calls the 
  <b>NdisTcpOffloadForwardComplete</b> function to complete one or more forward requests that were made to the
  
  <mshelp:link keywords="netvista.miniporttcpoffloadforward" tabindex="0"><i>
  MiniportTcpOffloadForward</i></mshelp:link> function of the offload target.


## -prototype


````
VOID NdisTcpOffloadForwardComplete(
  _In_ NDIS_HANDLE      NdisMiniportHandle,
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters




### -param NdisMiniportHandle [in]

The handle that the offload target obtained in a previous call to the 
     <mshelp:link keywords="netvista.ndismregisterminiportdriver" tabindex="0"><b>
     NdisMRegisterMiniportDriver</b></mshelp:link> function.


### -param NetBufferList [in]

A pointer to a 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure. This structure
     can be stand-alone or the first structure in a linked list of NET_BUFFER_LIST structures. The offload
     target obtained these structures in one or more calls to its 
     <mshelp:link keywords="netvista.miniporttcpoffloadforward" tabindex="0"><i>
     MiniportTcpOffloadForward</i></mshelp:link> function.


## -returns


None



## -remarks


To improve system performance, an offload target can create a linked list that contains 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures from multiple
    calls to the 
    <mshelp:link keywords="netvista.miniporttcpoffloadforward" tabindex="0"><i>
    MiniportTcpOffloadForward</i></mshelp:link> function. The offload target can then pass such a linked list in a single
    call to the 
    <b>NdisTcpOffloadForwardComplete</b> function.

An offload target must write one of the following status values to each NET_BUFFER_LIST structure that
    it passes to the 
    <b>NdisTcpOffloadForwardComplete</b> function:





## -see-also

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

<a href="..\ndischimney\nc-ndischimney-w_tcp_offload_forward_handler.md">MiniportTcpOffloadForward</a>

<a href="..\ndis\nf-ndis-ndismregisterminiportdriver.md">NdisMRegisterMiniportDriver</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_TCP_OFFLOAD_FORWARD_COMPLETE callback function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

