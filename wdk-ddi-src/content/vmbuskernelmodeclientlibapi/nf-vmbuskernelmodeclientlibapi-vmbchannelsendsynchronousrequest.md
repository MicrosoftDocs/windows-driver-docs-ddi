---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSendSynchronousRequest
title: VmbChannelSendSynchronousRequest function
author: windows-driver-content
description: The VmbChannelSendSynchronousRequest function sends a packet to the opposite endpoint and waits for a response.
old-location: netvista\vmbchannelsendsynchronousrequest.htm
old-project: netvista
ms.assetid: 312DED8E-570E-4DEC-B084-36894970F49F
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelSendSynchronousRequest, VmbChannelSendSynchronousRequest function [Network Drivers Starting with Windows Vista], netvista.vmbchannelsendsynchronousrequest, vmbuskernelmodeclientlibapi/VmbChannelSendSynchronousRequest
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
-	VmbChannelSendSynchronousRequest
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelSendSynchronousRequest function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSendSynchronousRequest</b> function sends a packet to the opposite endpoint and waits for a response.



## -parameters




### -param Channel [in]

A handle for the channel.  


### -param Buffer [in]

Data to send.



### -param BufferSize [in]

The size, in bytes, of the data to send.



### -param ExternalDataMdl [in, optional]

A Memory Descriptor List (MDL) that describes an additional buffer to     send.



### -param Flags [in]

Standard flags.


### -param CompletionBuffer [out]

Buffer in which to store completion packet results.



### -param CompletionBufferSize [in, out, optional]

The size, in bytes, of the <i>CompletionBuffer</i> value. This value must be     rounded up to nearest 8 bytes, or else the function fails. On success,
returns the number of bytes written into <i>CompletionBuffer</i>.



### -param Timeout [in, optional]

A timeout in the style of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a> routing.
After this time elapses, the packet is cancelled. For a timeout of zero (0), if a packet does not fir in the ring buffer, it is not queued.


## -returns



<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_SUCCESS</b></dt>
</dl>
</td>
<td width="60%">
The functions finished successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The packet did not fit in the buffer and
was not queued.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_CANCELLED</b></dt>
</dl>
</td>
<td width="60%">
The packet was canceled.


</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_REMOVED</b></dt>
</dl>
</td>
<td width="60%">
The channel is being shut down.

</td>
</tr>
</table>
 




## -remarks



Clients can run this function with any combination of parameters. 

The root may only call
this if <code>*Timeout == 0</code> and the <b>VMBUS_CHANNEL_FORMAT_FLAG_WAIT_FOR_COMPLETION</b> flag is not set.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553350">KeWaitForSingleObject</a>
 

 

