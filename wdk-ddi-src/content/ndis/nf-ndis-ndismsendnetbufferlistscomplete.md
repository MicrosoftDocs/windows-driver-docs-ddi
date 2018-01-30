---
UID: NF:ndis.NdisMSendNetBufferListsComplete
title: NdisMSendNetBufferListsComplete function
author: windows-driver-content
description: Miniport drivers call the NdisMSendNetBufferListsComplete function to return a linked list of NET_BUFFER_LIST structures to an overlying driver and to return the final status of a send request.
old-location: netvista\ndismsendnetbufferlistscomplete.htm
old-project: netvista
ms.assetid: 33890582-5eba-4cc1-a0d9-ec07f18da453
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisMSendNetBufferListsComplete function [Network Drivers Starting with Windows Vista], ndis_sendrcv_ref_11bdd96b-0ba8-475a-ba6e-03492e2993d7.xml, NdisMSendNetBufferListsComplete, ndis/NdisMSendNetBufferListsComplete, netvista.ndismsendnetbufferlistscomplete
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
req.ddi-compliance: Irql_SendRcv_Function, NdisTimedDataHang, NdisTimedDataSend
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
-	NdisMSendNetBufferListsComplete
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisMSendNetBufferListsComplete function


## -description


Miniport drivers call the 
  <b>NdisMSendNetBufferListsComplete</b> function to return a linked list of 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures to an overlying
  driver and to return the final status of a send request.


## -syntax


````
VOID NdisMSendNetBufferListsComplete(
  _In_ NDIS_HANDLE      MiniportAdapterHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            SendCompleteFlags
);
````


## -parameters




### -param MiniportAdapterHandle [in]

The miniport handle that NDIS passed to the 
     <mshelp:link keywords="netvista.miniportinitializeex" tabindex="0"><i>
     MiniportInitializeEx</i></mshelp:link> function.


### -param NetBufferList

TBD


### -param SendCompleteFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_SEND_COMPLETE_FLAGS_DISPATCH_LEVEL flag which; if set, indicates
     that the current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.


#### - NetBufferLists [in]

A pointer to a linked list of NET_BUFFER_LIST structures. The miniport driver received the
     NET_BUFFER_LIST structures in previous calls to its 
     <mshelp:link keywords="netvista.miniportsendnetbufferlists" tabindex="0"><i>
     MiniportSendNetBufferLists</i></mshelp:link> function.


## -returns


None



## -remarks


A miniport driver calls 
    <b>NdisMSendNetBufferListsComplete</b> to complete send requests that NDIS made to the driver's 
    <mshelp:link keywords="netvista.miniportsendnetbufferlists" tabindex="0"><i>
    MiniportSendNetBufferLists</i></mshelp:link> function. The miniport driver specifies a linked list of 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that are
    associated with the completed send requests. While the status of the send requests is pending, the
    miniport driver retains ownership of the NET_BUFFER_LIST structures and all the protocol-allocated
    resources that are associated with the NET_BUFFER_LIST structures.

After a miniport driver calls 
    <b>NdisMSendNetBufferListsComplete</b>, NDIS calls the 
    <mshelp:link keywords="netvista.protocolsendnetbufferlistscomplete" tabindex="0"><b>
    ProtocolSendNetBufferListsComplete</b></mshelp:link> function of the driver that called the 
    <a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">NdisSendNetBufferLists</a> function to
    initiate the send request.

The miniport driver can complete send requests in any order. For example, the miniport driver could
    concatenate the NET_BUFFER_LIST structure lists from multiple 
    <i>MiniportSendNetBufferLists</i> calls or split up a list from a 
    <i>MiniportSendNetBufferLists</i> call. However, the miniport driver must not modify the list of 
    <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are associated with a
    NET_BUFFER_LIST structure.

The miniport driver must set one of the following status codes in the 
    <b>Status</b> member of each NET_BUFFER_LIST structure that the 
    <i>NetBufferLists</i> parameter specifies:



A miniport driver's call to 
    <b>NdisMSendNetBufferListsComplete</b> does not necessarily mean that the data for a send request has been
    transmitted over the network. The data might be queued in the NIC hardware.



## -see-also

<a href="..\ndis\nf-ndis-ndissendnetbufferlists.md">NdisSendNetBufferLists</a>

<a href="..\ndis\nc-ndis-miniport_initialize.md">MiniportInitializeEx</a>

<a href="..\ndis\nc-ndis-miniport_send_net_buffer_lists.md">MiniportSendNetBufferLists</a>

<a href="..\ndis\nc-ndis-miniport_cancel_send.md">MiniportCancelSend</a>

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisMSendNetBufferListsComplete function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

