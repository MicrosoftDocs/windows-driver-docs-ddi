---
UID: NF:ndis.NdisGetPoolFromNetBufferList
title: NdisGetPoolFromNetBufferList function
author: windows-driver-content
description: Call the NdisGetPoolFromNetBufferList function to get the NET_BUFFER_LIST structure pool handle that is associated with a specified NET_BUFFER_LIST structure.
old-location: netvista\ndisgetpoolfromnetbufferlist.htm
old-project: netvista
ms.assetid: 645fd5f6-32b5-4ef6-9583-1418291d55d3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.ndisgetpoolfromnetbufferlist, NdisGetPoolFromNetBufferList function [Network Drivers Starting with Windows Vista], ndis/NdisGetPoolFromNetBufferList, ndis_netbuf_functions_ref_c93c9420-04fb-42f7-9844-29c3b2052b82.xml, NdisGetPoolFromNetBufferList
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
req.ddi-compliance: Irql_NetBuffer_Function
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
-	NdisGetPoolFromNetBufferList
product: Windows
targetos: Windows
req.typenames: NDIS_SHARED_MEMORY_USAGE, *PNDIS_SHARED_MEMORY_USAGE
---

# NdisGetPoolFromNetBufferList function


## -description


Call the 
  <b>NdisGetPoolFromNetBufferList</b> function to get the 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure pool handle that is
  associated with a specified NET_BUFFER_LIST structure.


## -syntax


````
NDIS_HANDLE NdisGetPoolFromNetBufferList(
  _In_ PNET_BUFFER_LIST NetBufferList
);
````


## -parameters




### -param NetBufferList [in]

A pointer to a previously allocated 
     <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -returns


<b>NdisGetPoolFromNetBufferList</b> returns a handle to the NET_BUFFER_LIST structure pool that is
     associated with the specified NET_BUFFER_LIST structure.



## -remarks


The handle that 
    <b>NdisGetPoolFromNetBufferList</b> returns is a required parameter in calls to NDIS functions that
    manipulate the 
    <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structures that are from the
    associated NET_BUFFER_LIST structure pool.



## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisGetPoolFromNetBufferList function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

