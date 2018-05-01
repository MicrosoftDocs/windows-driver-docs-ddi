---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelCreateGpadlFromBuffer
title: VmbChannelCreateGpadlFromBuffer function
author: windows-driver-content
description: The VmbChannelCreateGpadlFromBuffer function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer.
old-location: netvista\vmbchannelcreategpadlfrombuffer.htm
old-project: netvista
ms.assetid: B45E2463-1EBC-4F32-B3AD-8331E664BB24
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VMBUS_CHANNEL_GPADL_READ_ONLY, VmbChannelCreateGpadlFromBuffer, VmbChannelCreateGpadlFromBuffer function [Network Drivers Starting with Windows Vista], netvista.vmbchannelcreategpadlfrombuffer, vmbuskernelmodeclientlibapi/VmbChannelCreateGpadlFromBuffer
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
-	VmbChannelCreateGpadlFromBuffer
product: Windows
targetos: Windows
req.typenames: 
---

# VmbChannelCreateGpadlFromBuffer function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCreateGpadlFromBuffer</b> function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used
in the server to access the buffer.  


## -parameters




### -param Channel [in]

 A handle for a channel.  


### -param Flags [in]

Flags. The possible values are the following:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_GPADL_READ_ONLY"></a><a id="vmbus_channel_gpadl_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_GPADL_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
If you specify this value, the buffer is read-only. Otherwise, the server can write to the buffer. This is not a security measure, but can improve snapshot and live migration performance.


</td>
</tr>
</table>
 


### -param Buffer [in]

 The buffer, which is probed and locked
until the GPADL is torn down.



### -param ByteCount [in]

The length of the buffer, in bytes.



### -param GpadlHandle [out]

A GPADL handle of the created Memory Descriptor List (MDL). Send this to the server to use with the <a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a> function.


## -remarks



When this function returns, the server
endpoint can call <a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a>, because VMBus will already have sent
the GPADL description to the opposite endpoint and received confirmation.


The GPADL must be deleted by using the <a href="https://msdn.microsoft.com/B1446A29-F2C1-4F08-8B38-5BE9188F5132">VmbChannelDeleteGpadl</a> function.




## -see-also




<a href="https://msdn.microsoft.com/B1446A29-F2C1-4F08-8B38-5BE9188F5132">VmbChannelDeleteGpadl</a>



<a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a>
 

 

