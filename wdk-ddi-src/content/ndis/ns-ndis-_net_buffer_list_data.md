---
UID: NS:ndis._NET_BUFFER_LIST_DATA
title: "_NET_BUFFER_LIST_DATA"
author: windows-driver-content
description: The NET_BUFFER_LIST_DATA structure contains management data for the NET_BUFFER structures that are linked to a NET_BUFFER_LIST structure.
old-location: netvista\net_buffer_list_data.htm
old-project: netvista
ms.assetid: 104b2bc0-e657-43c6-a274-ddbcef76293b
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNET_BUFFER_LIST_DATA, NET_BUFFER_LIST_DATA, NET_BUFFER_LIST_DATA structure [Network Drivers Starting with Windows Vista], PNET_BUFFER_LIST_DATA, PNET_BUFFER_LIST_DATA structure pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_LIST_DATA, ndis/NET_BUFFER_LIST_DATA, ndis/PNET_BUFFER_LIST_DATA, ndis_netbuf_structures_ref_1ce577dd-1eec-4ba6-94cb-3e37c205630d.xml, netvista.net_buffer_list_data"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.0 and later.
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
req.irql: See Remarks section
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NET_BUFFER_LIST_DATA
product: Windows
targetos: Windows
req.typenames: NET_BUFFER_LIST_DATA, *PNET_BUFFER_LIST_DATA
---

# _NET_BUFFER_LIST_DATA structure


## -description


The NET_BUFFER_LIST_DATA structure contains management data for the 
  <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structures that are linked to a 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.


## -syntax


````
typedef struct _NET_BUFFER_LIST_DATA {
  PNET_BUFFER_LIST Next;
  PNET_BUFFER      FirstNetBuffer;
} NET_BUFFER_LIST_DATA, *PNET_BUFFER_LIST_DATA;
````


## -struct-fields




### -field Next

A pointer to the next NET_BUFFER_LIST structure in a linked list of NET_BUFFER_LIST structures. If
     this structure is the last NET_BUFFER_LIST structure in the list, this member is <b>NULL</b>.


### -field FirstNetBuffer

A pointer to the first 
     <a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a> structure in the linked list of
     NET_BUFFER structures.


## -remarks



The 
    <a href="..\ndis\ns-ndis-_net_buffer_list_header.md">NET_BUFFER_LIST_HEADER</a> structure
    contains a NET_BUFFER_LIST_DATA structure.




## -see-also

<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>



<a href="..\ndis\ns-ndis-_net_buffer.md">NET_BUFFER</a>



<a href="..\ndis\ns-ndis-_net_buffer_list_header.md">NET_BUFFER_LIST_HEADER</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_LIST_DATA structure%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

