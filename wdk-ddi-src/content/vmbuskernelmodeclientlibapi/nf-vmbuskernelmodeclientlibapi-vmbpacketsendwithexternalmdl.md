---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketSendWithExternalMdl
title: VmbPacketSendWithExternalMdl function
author: windows-driver-content
description: The VmbPacketSendWithExternalMdl function sends the data in a packet buffer or external data Memory Descriptor List (MDL).
old-location: netvista\vmbpacketsendwithexternalmdl.htm
old-project: netvista
ms.assetid: C1B3FA0C-65B8-4CE1-B8F5-650DF54C9E1E
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VMBUS_CHANNEL_FORMAT_FLAG_FORCE_MDL_LENGTH, VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER, VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION, VmbPacketSendWithExternalMdl, VmbPacketSendWithExternalMdl function [Network Drivers Starting with Windows Vista], netvista.vmbpacketsendwithexternalmdl, vmbuskernelmodeclientlibapi/VmbPacketSendWithExternalMdl
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
-	VmbPacketSendWithExternalMdl
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbPacketSendWithExternalMdl function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSendWithExternalMdl</b> function sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet
throughout the lifetime of the transaction.


## -parameters




### -param PacketObject [in]

A handle to the VMBus packet object.




### -param Buffer [in]

A buffer that contains the command packet that is sent
through the VMBus ring buffer.


### -param BufferLength [in]

The length, in bytes, of the buffer in the <i>Buffer</i> parameter. 


### -param ExternalDataMdl [in]

 An MDL that describes a data buffer associated with     the packet. 


### -param MdlOffset [in]

The offset from the buffer described by the MDL where the
data starts.



### -param MdlLength [in]

The length of the sub-buffer to send. Use 0 for the entire     MDL.



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
completion packet comes back from the opposite endpoint. This flag must be set.

</td>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_FORMAT_FLAG_FORCE_MDL_LENGTH"></a><a id="vmbus_channel_format_flag_force_mdl_length"></a><dl>
<dt><b>VMBUS_CHANNEL_FORMAT_FLAG_FORCE_MDL_LENGTH</b></dt>
</dl>
</td>
<td width="60%">
Always use <i>MdlLength</i> for the
length of the external data MDL, even if this length is longer than the
<b>ByteCount</b> field of the MDL. This only allows exceeding the length of the MDL by
rounding up to a page boundary. If this flag is set, only the first MDL in the
MDL chain is used.


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



<b>VmbPacketSendWithExternalMdl</b> returns a status code.




## -remarks



This function differs from the <a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a> function in that it allows passing an MDL offset and MDL length.




## -see-also




<a href="https://msdn.microsoft.com/EBB981CB-0107-497A-B6E6-9271E22A8D5F">VmbPacketSend</a>
 

 

