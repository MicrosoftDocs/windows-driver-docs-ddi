---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelRestoreFromBuffer
title: VmbChannelRestoreFromBuffer function
author: windows-driver-content
description: The VmbChannelRestoreFromBuffer function restores the client state from previously saved state. The driver must check the return value of the function.
old-location: netvista\vmbchannelrestorefrombuffer.htm
old-project: netvista
ms.assetid: 5A063585-AC45-44DF-BE21-FA1BB6283E6F
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: vmbuskernelmodeclientlibapi/VmbChannelRestoreFromBuffer, VmbChannelRestoreFromBuffer, VmbChannelRestoreFromBuffer function [Network Drivers Starting with Windows Vista], netvista.vmbchannelrestorefrombuffer
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	VmbusKernelModeClientLibApi.h
apiname:
-	VmbChannelRestoreFromBuffer
product: Windows
targetos: Windows
req.typenames: "*PVIDEO_PORT_AGP_SERVICES, VIDEO_PORT_AGP_SERVICES"
req.product: Windows 10 or later.
---

# VmbChannelRestoreFromBuffer function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelRestoreFromBuffer</b>  function restores the client state from previously saved state.
The driver must check the return value of the function.


## -syntax


````
NTSTATUS VmbChannelRestoreFromBuffer(
  _In_ VMBCHANNEL                        Channel,
  _In_ reads_bytes_(BufferSize)    PVOID Buffer,
  _In_ ULONG                             BufferSize
);
````


## -parameters




### -param Channel [in]

 A handle for a channel.  


### -param Buffer [in]

A pointer to a buffer that contains previously saved state.



### -param BufferSize [in]

The size, in bytes, of the buffer.


## -returns


<b>VmbChannelRestoreFromBuffer</b> returns one of the following status values: 
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
The function finished successfully.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MORE_PROCESSING_REQUIRED</b></dt>
</dl>
</td>
<td width="60%">
State was restored successfully,     but more chunks were saved.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>Other status code for which NT_SUCCESS is FALSE</b></dt>
</dl>
</td>
<td width="60%">
The function failed.

</td>
</tr>
</table> 



## -remarks


The caller is expected to call this function with buffers that contain whole
"chunks" of stored data.


