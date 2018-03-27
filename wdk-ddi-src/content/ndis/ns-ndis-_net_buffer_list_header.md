---
UID: NS:ndis._NET_BUFFER_LIST_HEADER
title: "_NET_BUFFER_LIST_HEADER"
author: windows-driver-content
description: The NET_BUFFER_LIST_HEADER defines header information for the NET_BUFFER_LIST structure.
old-location: netvista\net_buffer_list_header.htm
old-project: netvista
ms.assetid: 49169618-c42d-4bae-b1df-1426059d60d7
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*PNET_BUFFER_LIST_HEADER, NET_BUFFER_LIST_HEADER, NET_BUFFER_LIST_HEADER union [Network Drivers Starting with Windows Vista], PNET_BUFFER_LIST_HEADER, PNET_BUFFER_LIST_HEADER union pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_LIST_HEADER, ndis/NET_BUFFER_LIST_HEADER, ndis/PNET_BUFFER_LIST_HEADER, ndis_netbuf_structures_ref_d7b08d29-e8af-4a7d-84bc-03c1885ee7e9.xml, netvista.net_buffer_list_header"
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
-	NET_BUFFER_LIST_HEADER
product: Windows
targetos: Windows
req.typenames: NET_BUFFER_LIST_HEADER, *PNET_BUFFER_LIST_HEADER
---

# _NET_BUFFER_LIST_HEADER structure


## -description


The NET_BUFFER_LIST_HEADER defines header information for the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -struct-fields




### -field NetBufferListData

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568393">NET_BUFFER_LIST_DATA</a> structure.


### -field Link

Reserved for NDIS.


## -remarks



NDIS maintains the information in the NET_BUFFER_LIST_HEADER union.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568393">NET_BUFFER_LIST_DATA</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NET_BUFFER_LIST_HEADER union%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

