---
UID: NF:vmbuskernelmodeclientlibapi.VmbPacketSend
title: VmbPacketSend function
author: windows-driver-content
description: The VmbPacketSend function sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet throughout the lifetime of the transaction.
old-location: netvista\vmbpacketsend.htm
old-project: netvista
ms.assetid: EBB981CB-0107-497A-B6E6-9271E22A8D5F
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: VmbPacketSend
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
req.alt-api: VmbPacketSend
req.alt-loc: vmbkmcl.lib,vmbkmcl.dll
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
req.typenames: *PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbPacketSend function



## -description
<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbPacketSend</b> function  sends the data in a packet buffer or external data Memory Descriptor List (MDL). The function associates that data with the VMBus packet object, which represents the packet
throughout the lifetime of the transaction.




## -syntax

````
NTSTATUS VmbPacketSend(
  _In_     __drv_aliasesMem VMBPACKET       PacketObject,
  _In_     reads_bytes_(BufferLength) PVOID Buffer,
  _In_     UINT32                           BufferLength,
  _In_opt_ PMDL                             ExternalDataMdl,
  _In_     UINT32                           Flags
);
````


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

### -param VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION

</td>
<td width="60%">
This packet cannot be considered complete and its resources cannot be released until a
completion packet comes back from the opposite endpoint.

</td>
</tr>
<tr>

### -param VMBUS_CHANNEL_FORMAT_FLAG_PAGED_BUFFER

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
For information on other ways to send packets, see the <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>, <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a>, and <a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a> functions.


## -see-also
<dl>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbchannelsendsynchronousrequest.md">VmbChannelSendSynchronousRequest</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalpfns.md">VmbPacketSendWithExternalPfns</a>
</dt>
<dt>
<a href="..\vmbuskernelmodeclientlibapi\nf-vmbuskernelmodeclientlibapi-vmbpacketsendwithexternalmdl.md">VmbPacketSendWithExternalMdl</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbPacketSend function%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

