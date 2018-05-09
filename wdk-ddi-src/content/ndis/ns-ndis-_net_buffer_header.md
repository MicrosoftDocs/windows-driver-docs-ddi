---
UID: NS:ndis._NET_BUFFER_HEADER
title: "_NET_BUFFER_HEADER"
author: windows-driver-content
description: The NET_BUFFER_HEADER structure specifies header information for the NET_BUFFER structure.
old-location: netvista\net_buffer_header.htm
old-project: netvista
ms.assetid: db7277d0-9671-4680-84d4-d3415ce3922f
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: "*PNET_BUFFER_HEADER, NET_BUFFER_HEADER, NET_BUFFER_HEADER union [Network Drivers Starting with Windows Vista], PNET_BUFFER_HEADER, PNET_BUFFER_HEADER union pointer [Network Drivers Starting with Windows Vista], _NET_BUFFER_HEADER, ndis/NET_BUFFER_HEADER, ndis/PNET_BUFFER_HEADER, ndis_netbuf_structures_ref_a19368c6-0bef-4fe6-be52-d76e0c6ea99d.xml, netvista.net_buffer_header"
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
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ndis.h
api_name:
-	NET_BUFFER_HEADER
product:
- Windows
targetos: Windows
req.typenames: NET_BUFFER_HEADER, *PNET_BUFFER_HEADER
---

# _NET_BUFFER_HEADER structure


## -description


The NET_BUFFER_HEADER structure specifies header information for the 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure.


## -struct-fields




### -field NetBufferData

A 
     <a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a> structure.


### -field Link

Reserved for NDIS.


## -remarks



NDIS maintains the information in the NET_BUFFER_HEADER union.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568381">NET_BUFFER_DATA</a>
 

 

