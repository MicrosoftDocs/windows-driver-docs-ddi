---
UID: NS:ndis._NET_BUFFER_LIST_HEADER
title: _NET_BUFFER_LIST_HEADER
author: windows-driver-content
description: The NET_BUFFER_LIST_HEADER defines header information for the NET_BUFFER_LIST structure.
old-location: netvista\net_buffer_list_header.htm
old-project: netvista
ms.assetid: 49169618-c42d-4bae-b1df-1426059d60d7
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: _NET_BUFFER_LIST_HEADER, *PNET_BUFFER_LIST_HEADER, NET_BUFFER_LIST_HEADER
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
req.alt-api: NET_BUFFER_LIST_HEADER
req.alt-loc: ndis.h
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
req.typenames: *PNET_BUFFER_LIST_HEADER, NET_BUFFER_LIST_HEADER
---

# _NET_BUFFER_LIST_HEADER structure



## -description
The NET_BUFFER_LIST_HEADER defines header information for the 
  <a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a> structure.



## -syntax

````
typedef union _NET_BUFFER_LIST_HEADER {
  NET_BUFFER_LIST_DATA NetBufferListData;
  SLIST_HEADER         Link;
} NET_BUFFER_LIST_HEADER, *PNET_BUFFER_LIST_HEADER;
````


## -struct-fields

### -field NetBufferListData

A 
     <a href="..\ndis\ns-ndis-_net_buffer_list_data.md">NET_BUFFER_LIST_DATA</a> structure.


### -field Link

Reserved for NDIS.


## -remarks
NDIS maintains the information in the NET_BUFFER_LIST_HEADER union.


## -see-also
<dl>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list.md">NET_BUFFER_LIST</a>
</dt>
<dt>
<a href="..\ndis\ns-ndis-_net_buffer_list_data.md">NET_BUFFER_LIST_DATA</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_LIST_HEADER union%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

