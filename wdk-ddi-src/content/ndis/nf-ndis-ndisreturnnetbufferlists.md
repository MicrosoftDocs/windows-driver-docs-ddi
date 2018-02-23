---
UID: NF:ndis.NdisReturnNetBufferLists
title: NdisReturnNetBufferLists function
author: windows-driver-content
description: NDIS drivers call the NdisReturnNetBufferLists function to release ownership of a list of NET_BUFFER_LIST structures, along with the associated NET_BUFFER structures and network data.
old-location: netvista\ndisreturnnetbufferlists.htm
old-project: netvista
ms.assetid: 1a45bc5c-cdc1-46d2-905b-3d5eea3645c1
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: NdisReturnNetBufferLists function [Network Drivers Starting with Windows Vista], ndis_sendrcv_ref_9c5a4908-356f-4e7c-9351-4fec4358180d.xml, NdisReturnNetBufferLists, ndis/NdisReturnNetBufferLists, netvista.ndisreturnnetbufferlists
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
req.ddi-compliance: Irql_SendRcv_Function
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
-	NdisReturnNetBufferLists
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisReturnNetBufferLists function


## -description


NDIS drivers call the 
  <b>NdisReturnNetBufferLists</b> function to release ownership of a list of 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures, along with the
  associated 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures and network data.


## -syntax


````
VOID NdisReturnNetBufferLists(
  _In_ NDIS_HANDLE      NdisBindingHandle,
  _In_ PNET_BUFFER_LIST NetBufferLists,
  _In_ ULONG            ReturnFlags
);
````


## -parameters




### -param NdisBindingHandle [in]

A handle that identifies the target adapter. This handle was returned by a previous call to the 
     <a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a> function. All of the 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that are
     specified in this call must be from the binding that this handle identifies.


### -param NetBufferLists [in]

A pointer to a linked list of NET_BUFFER_LIST structures that are to be returned to the underlying
     driver. The linked list can contain NET_BUFFER_LIST structures from multiple previous calls to the 
     <a href="..\ndis\nc-ndis-protocol_receive_net_buffer_lists.md">
     ProtocolReceiveNetBufferLists</a> function.


### -param ReturnFlags [in]

NDIS flags that can be combined with an OR operation. To clear all the flags, set this member to
     zero. This function supports the NDIS_RETURN_FLAGS_DISPATCH_LEVEL flag which; if set, indicates that the
     current IRQL is DISPATCH_LEVEL. For more information about this flag, see 
     <a href="https://msdn.microsoft.com/ac559f4f-0138-4b9a-8f1b-44a2973fd6a1">Dispatch IRQL Tracking</a>.


## -returns



None




## -remarks



If the NDIS_RECEIVE_FLAGS_RESOURCES flag in the 
    <i>ReceiveFlags</i> parameter that NDIS passed to the 
    <a href="..\ndis\nc-ndis-protocol_receive_net_buffer_lists.md">
    ProtocolReceiveNetBufferLists</a> function was not set, the protocol driver must call 
    <b>NdisReturnNetBufferLists</b> to return the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures and associated
    data. After the protocol driver calls 
    <b>NdisReturnNetBufferLists</b>, NDIS calls the underlying miniport driver's 
    <a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
    MiniportReturnNetBufferLists</a> function.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\nc-ndis-miniport_return_net_buffer_lists.md">
   MiniportReturnNetBufferLists</a>



<a href="..\ndis\nf-ndis-ndisopenadapterex.md">NdisOpenAdapterEx</a>



<a href="..\ndis\nc-ndis-protocol_receive_net_buffer_lists.md">
   ProtocolReceiveNetBufferLists</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisReturnNetBufferLists function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

