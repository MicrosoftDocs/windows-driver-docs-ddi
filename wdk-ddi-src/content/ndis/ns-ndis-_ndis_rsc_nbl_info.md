---
UID: NS:ndis._NDIS_RSC_NBL_INFO
title: "_NDIS_RSC_NBL_INFO"
author: windows-driver-content
description: The NDIS_RSC_NBL_INFO union specifies receive segment coalescing (RSC) counter information that is associated with a NET_BUFFER_LIST structure.
old-location: netvista\ndis_rsc_nbl_info.htm
tech.root: netvista
ms.assetid: ba9c18ba-8940-4aef-9d58-3105ee1420ce
ms.date: 5/2/2018
ms.keywords: "*PNDIS_RSC_NBL_INFO, NDIS_RSC_NBL_INFO, NDIS_RSC_NBL_INFO union [Network Drivers Starting with Windows Vista], PNDIS_RSC_NBL_INFO, PNDIS_RSC_NBL_INFO union pointer [Network Drivers Starting with Windows Vista], _NDIS_RSC_NBL_INFO, ndis/NDIS_RSC_NBL_INFO, ndis/PNDIS_RSC_NBL_INFO, netvista.ndis_rsc_nbl_info"
ms.topic: struct
req.header: ndis.h
req.include-header: Ndis.h
req.target-type: Windows
req.target-min-winverclnt: Supported for NDIS 6.30 and later drivers in Windows 8.
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
-	NDIS_RSC_NBL_INFO
product:
- Windows
targetos: Windows
req.typenames: NDIS_RSC_NBL_INFO, *PNDIS_RSC_NBL_INFO
---

# _NDIS_RSC_NBL_INFO structure


## -description


The <b>NDIS_RSC_NBL_INFO</b> union specifies receive segment coalescing (RSC) counter information that is associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure.




## -struct-fields




### -field Info

 
A member in the union that is contained in <b>NDIS_RSC_NBL_INFO</b>.  Drivers use <b>Info</b> to access RSC information. <b>Info</b> is a structure with the following members:




### -field Info.CoalescedSegCount

The number of coalesced segments in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. For non-RSC packets this member must be set to zero.
Drivers can access this member with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439944">NET_BUFFER_LIST_COALESCED_SEG_COUNT</a>
macro. 

<div class="alert"><b>Note</b>  The <b>RscTcpTimestampDelta</b> information  and the <b>DupAckCount</b> member should be non-zero only if <b>CoalescedSegCount</b> is not zero.
See the remarks section for more information about <b>RscTcpTimestampDelta</b>.</div>
<div> </div>

### -field Info.DupAckCount

The number of duplicate ACKs that were encountered while forming the  <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure. <b>DupAckCount</b> should be non-zero only if <b>CoalescedSegCount</b> is not zero.
Drivers can access this member with the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439945">NET_BUFFER_LIST_DUP_ACK_COUNT</a>
macro.


### -field Value

A member in the union that is contained in <b>NDIS_RSC_NBL_INFO</b>.  Drivers use <b>Value</b> to access the RSC information as a single <b>PVOID</b>.  


## -remarks



To access receive segment coalescing (RSC) counter  information that is associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure, an NDIS driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies the <b>TcpRecvSegCoalesceInfo</b> information type which is in an <b>NDIS_RSC_NBL_INFO</b> union.



To access RSC  timestamp information that is associated with a <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure, an NDIS driver calls the <a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a> macro and specifies the <b>RscTcpTimestampDelta</b> information type which is a single <b>ULONG</b> value.

<div class="alert"><b>Note</b>  The <b>RscTcpTimestampDelta</b> information  and the <b>DupAckCount</b> member of <b>NDIS_RSC_NBL_INFO</b> should be nonzero only if <b>CoalescedSegCount</b> is not zero.
</div>
<div> </div>
The <b>RscTcpTimestampDelta</b> information might be set for coalesced segments that are using the TCP timestamp option. <b>RscTcpTimestampDelta</b> information should contain the delta between the earliest and the latest TCP timestamp values in the sequence of coalesced segments. The miniport driver can provide a 16-bit value for <b>RscTcpTimestampDelta</b>.  

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> structure of a single coalesced unit (SCU) is not different from the standard <b>NET_BUFFER_LIST</b> structure that is indicated on the receive path without RSC. The SCU resembles an IP jumbogram packet that came from the wire. Therefore, every indicated SCU must have one <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> structure for each <b>NET_BUFFER_LIST</b>. 

The <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a>  can be an MDL chain and the MDL can have a total size that exceeds the normal maximum transmission unit (MTU) but must be limited by the maximum legal IP datagram length, see RFC791 section 3.1.


Also, the additional <a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a> information can be provided for an SCU. 
NDIS performs the <b>NET_BUFFER_LIST</b> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff568376">NET_BUFFER</a> validation. The host TCPIP stack performs packet checks including IP and TCP header validation. 





## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff568388">NET_BUFFER_LIST</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439944">NET_BUFFER_LIST_COALESCED_SEG_COUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439945">NET_BUFFER_LIST_DUP_ACK_COUNT</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff568401">NET_BUFFER_LIST_INFO</a>
 

 

