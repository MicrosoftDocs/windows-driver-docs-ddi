---
UID: NF:ndis.NdisQueryNetBufferPhysicalCount
title: NdisQueryNetBufferPhysicalCount function
author: windows-driver-content
description: The NdisQueryNetBufferPhysicalCount function returns the maximum number of physical breaks mapped by the buffer descriptors that are associated with the given NET_BUFFER structure.
old-location: netvista\ndisquerynetbufferphysicalcount.htm
old-project: netvista
ms.assetid: 99869b20-3458-426a-ad64-c2cc54213290
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: ndis/NdisQueryNetBufferPhysicalCount, ndis_netbuf_functions_ref_d041f487-3273-402e-8726-d9a252b1dd45.xml, netvista.ndisquerynetbufferphysicalcount, NdisQueryNetBufferPhysicalCount, NdisQueryNetBufferPhysicalCount function [Network Drivers Starting with Windows Vista]
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
-	NdisQueryNetBufferPhysicalCount
product: Windows
targetos: Windows
req.typenames: "*PNDIS_SHARED_MEMORY_USAGE, NDIS_SHARED_MEMORY_USAGE"
---

# NdisQueryNetBufferPhysicalCount function


## -description


The 
  <b>NdisQueryNetBufferPhysicalCount</b> function returns the maximum number of physical breaks mapped by the
  buffer descriptors that are associated with the given 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


## -syntax


````
ULONG NdisQueryNetBufferPhysicalCount(
  _In_ PNET_BUFFER NetBuffer
);
````


## -parameters




### -param NetBuffer [in]

A pointer to a previously allocated 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure.


## -returns



<b>NdisQueryNetBufferPhysicalCount</b> returns a ULONG value containing a count of the maximum number of
     physical breaks, mapped by MDLs that are associated with the specified NET_BUFFER structure.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NdisQueryNetBufferPhysicalCount function%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

