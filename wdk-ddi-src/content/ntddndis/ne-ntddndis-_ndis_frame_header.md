---
UID: NE:ntddndis._NDIS_FRAME_HEADER
title: _NDIS_FRAME_HEADER
author: windows-driver-content
description: The NDIS_FRAME_HEADER enumeration identifies the type of header in a network data frame.
old-location: netvista\ndis_frame_header.htm
old-project: netvista
ms.assetid: 8897ae0c-6068-4fea-8944-1340595dbff3
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: NdisFrameHeaderIPv6, PNDIS_FRAME_HEADER enumeration pointer [Network Drivers Starting with Windows Vista], ntddndis/NdisFrameHeaderUndefined, NdisFrameHeaderArp, ntddndis/NDIS_FRAME_HEADER, netvista.ndis_frame_header, NdisFrameHeaderUndefined, ntddndis/PNDIS_FRAME_HEADER, PNDIS_FRAME_HEADER, ntddndis/NdisFrameHeaderIPv4, ntddndis/NdisFrameHeaderMaximum, ntddndis/NdisFrameHeaderMac, NdisFrameHeaderIPv4, virtual_machine_queue_ref_0ee94de6-7791-4a6e-b3da-2c8639843130.xml, *PNDIS_FRAME_HEADER, ntddndis/NdisFrameHeaderArp, ntddndis/NdisFrameHeaderUdp, ntddndis/NdisFrameHeaderIPv6, NdisFrameHeaderMac, NDIS_FRAME_HEADER enumeration [Network Drivers Starting with Windows Vista], NdisFrameHeaderMaximum, _NDIS_FRAME_HEADER, NDIS_FRAME_HEADER, NdisFrameHeaderUdp
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.20 and later.
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
req.irql: PASSIVE_LEVEL
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Ntddndis.h
apiname: 
-	NDIS_FRAME_HEADER
product: Windows
targetos: Windows
req.typenames: *PNDIS_FRAME_HEADER, NDIS_FRAME_HEADER
---

# _NDIS_FRAME_HEADER enumeration


## -description


The <b>NDIS_FRAME_HEADER</b> enumeration identifies the type of header in a network data frame.


## -syntax


````
typedef enum _NDIS_FRAME_HEADER { 
  NdisFrameHeaderUndefined,
  NdisFrameHeaderMac,
  NdisFrameHeaderArp,
  NdisFrameHeaderIPv4,
  NdisFrameHeaderIPv6,
  NdisFrameHeaderUdp,
  NdisFrameHeaderMaximum
} NDIS_FRAME_HEADER, *PNDIS_FRAME_HEADER;
````


## -enum-fields




### -field NdisFrameHeaderUndefined

An undefined frame header type.


### -field NdisFrameHeaderMac

A media access control (MAC) header.


### -field NdisFrameHeaderArp

An Address Resolution Protocol (ARP) header.


### -field NdisFrameHeaderIPv4

An IP version 4 (IPv4) header.


### -field NdisFrameHeaderIPv6

An IP version 6 (IPv6) header.


### -field NdisFrameHeaderUdp

A User Datagram Protocol
(UDP) header.


### -field NdisFrameHeaderMaximum

The maximum value for this enumeration. This value might change in future versions of the NDIS
     header files and binaries.


## -remarks


The NDIS_FRAME_HEADER enumeration is used in the 
    <mshelp:link keywords="netvista.ndis_receive_filter_field_parameters" tabindex="0"><b>
    NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b></mshelp:link> structure.



## -see-also

<mshelp:link keywords="netvista.ndis_receive_filter_field_parameters" tabindex="0"><b>
   NDIS_RECEIVE_FILTER_FIELD_PARAMETERS</b></mshelp:link>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20NDIS_FRAME_HEADER enumeration%20 RELEASE:%20(1/18/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

