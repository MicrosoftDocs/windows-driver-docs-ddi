---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketSend
title: VmbPacketSend function
author: windows-driver-content
description: The VmbPacketSend function sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet throughout the lifetime of the transaction.
old-location: netvista\vmbpacketsend.htm
old-project: netvista
ms.assetid: EBB981CB-0107-497A-B6E6-9271E22A8D5F
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER, VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION, VmbPacketSend, VmbPacketSend function [Network Drivers Starting with Windows Vista], netvista.vmbpacketsend, vmbuskernelmodeclientlibapi/VmbPacketSend
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8.1
req.target-min-winversvr: Windows Server 2012 R2
req.kmdf-ver: 1.13
req.umdf-ver: 2.0
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Vmbkmcl.lib
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	vmbkmcl.lib
-	vmbkmcl.dll
api_name:
-	VmbPacketSend
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbPacketSend function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSend</b> function  sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet
throughout the lifetime of the transaction.



## -parameters




### -param PacketObject [in]

A handle to the VMBus packet object.



### -param Buffer [in]

A buffer that contains the command packet that is sent
through the VMBus ring buffer.
 


### -param BufferLength [in]

The length, in bytes, of the buffer in the <i>Buffer</i> parameter. 


### -param ExternalDataMdl [in, optional]

An MDL that describes a data buffer associated with     the packet. 


### -param Flags [in]

 Flags. The following are pertinent flags:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION"></a><a id="vmbus_channel_format_flag_wait_for_completion"></a><dl>
<dt><b>VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION</b></dt>
</dl>
</td>
<td width="60%">
This packet cannot be considered complete and its resources cannot be released until a
completion packet comes back from the opposite endpoint.

</td>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER"></a><a id="vmbus_channel_format_flag_paged_buffer"></a><dl>
<dt><b>VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER</b></dt>
</dl>
</td>
<td width="60%">
The inline buffer is
paged and must be treated accordingly, which means it must be copied before entering DPC level.
Probing user-mode buffers or handling access violations is the
responsibility of the caller.

</td>
</tr>
</table>
 


## -returns



<b>VmbPacketSend</b> returns NT Status code.




## -remarks



For information on other ways to send packets, see the <a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>, <a href="https://msdn.microsoft.com/312DED8E-570E-4DEC-B084-36894970F49F">VmbChannelSendSynchronousRequest</a>, and <a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a> functions.




## -see-also




<a href="https://msdn.microsoft.com/312DED8E-570E-4DEC-B084-36894970F49F">VmbChannelSendSynchronousRequest</a>



<a href="https://msdn.microsoft.com/C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E">VmbPacketSendWithExternalMdl</a>



<a href="https://msdn.microsoft.com/50AACCAB-EFEA-42B7-8A34-FE110C7CDEED">VmbPacketSendWithExternalPfns</a>
 

 

