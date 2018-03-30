---
UID: NS:ndis._NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
title: "_NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO"
author: windows-driver-content
description: The NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure specifies IPsec header information in the OOB data of a NET_BUFFER_LIST structure.
old-location: netvista\ndis_ipsec_offload_v2_header_net_buffer_list_info.htm
old-project: netvista
ms.assetid: 657c7941-5475-4351-a429-94003a5c21d9
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: "*PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure [Network Drivers Starting with Windows Vista], PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure pointer [Network Drivers Starting with Windows Vista], _NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, ndis/NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, ndis/PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, netvista.ndis_ipsec_offload_v2_header_net_buffer_list_info, task_offload_IPsecv2_ref_696f856b-fb77-437d-ba9d-0b00b71d1cab.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported in NDIS 6.1 and later.
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
-	NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
product: Windows
targetos: Windows
req.typenames: NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO, *PNDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
---

# _NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure


## -description


<p class="CCE_Message">[The IPsec Task Offload feature is deprecated and should not be used.]

The NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure specifies IPsec header information in
  the OOB data of a 
  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.


## -struct-fields




### -field Transmit

A structure that contains the following members:


### -field Transmit.NextHeader

The next header value that is carried in the ESP trailer.


### -field Transmit.PadLength

The amount of padding, in bytes, that is added to the end of the payload for ESP only. 
       <b>PadLength</b> is specified for IPsec offload packets with and without large send offload (LSO).


### -field Transmit.AhHeaderOffset

The offset count from the beginning of the IP header to the AH header. The 
       <b>AhHeaderOffset</b> value is this offset, in bytes, divided by 4 to reduce the number of bits that
       are required to represent the offset. Note that the AH header is, at minimum, aligned on 4-byte
       boundaries.


### -field Transmit.EspHeaderOffset

The offset count from the beginning of the IP header to the ESP header. The 
       <b>EspHeaderOffset</b> value is this offset, in bytes, divided by 4 to reduce the number of bits that
       are required to represent the offset. Note that the ESP header is, at minimum, aligned on 4-byte
       boundaries.


### -field Receive

A structure that contains the following members:


### -field Receive.NextHeader

The next header value that is carried in the ESP trailer.


### -field Receive.PadLength

The amount of padding, in bytes, that is added to the end of the payload for ESP only. 
       <b>PadLength</b> is specified for IPsec offload packets with and without large send offload (LSO).


### -field Receive.HeaderInfoSet

A ULONG value that, when set, indicates the members of the 
       <b>Receive</b> structure are valid. If this member is not set, the 
       <b>Receive</b> structure is ignored.


## -remarks



The information in the NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure makes it easy for
    the miniport driver to parse an outbound packet. NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO
    specifies the header offsets for IPsec headers in the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure as well as the
    location of the next header and the padding length.

To set and get the IPsec tunnel information, use the 
    <b>IPsecOffloadV2HeaderNetBufferListInfo</b> index with the 
    <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro.
    NET_BUFFER_LIST_INFO returns an NDIS_IPSEC_OFFLOAD_V2_HEADER_NET_BUFFER_LIST_INFO structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
 

 

