---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelCreateGpadlFromMdl
title: VmbChannelCreateGpadlFromMdl function
author: windows-driver-content
description: The VmbChannelCreateGpadlFromMdl function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used in the server to access the buffer.
old-location: netvista\vmbchannelcreategpadlfrommdl.htm
old-project: netvista
ms.assetid: 6C63E250-1A11-45E8-B535-263806DA4A33
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VMBUS_CHANNEL_GPADL_READ_ONLY, VmbChannelCreateGpadlFromMdl, VmbChannelCreateGpadlFromMdl function [Network Drivers Starting with Windows Vista], netvista.vmbchannelcreategpadlfrommdl, vmbuskernelmodeclientlibapi/VmbChannelCreateGpadlFromMdl
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
-	VmbChannelCreateGpadlFromMdl
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelCreateGpadlFromMdl function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelCreateGpadlFromMdl</b> function creates a Guest Physical Address Descriptor List (GPADL) that describes a client-side buffer. The GPADL can be used
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
 


### -param Mdl [in]

 A pointer to a Memory Descriptor List (MDL) chain that describes the buffer. The buffer may
have multiple pieces, which are chained by using the MDL next pointer.



### -param StartOffsetWithinMdl [in]

An offset, in bytes, in the MDL at which to start the mapping.



### -param DataLengthWithinMdl [in]

The length, in bytes, of the buffer chain. If this value is zero (0),
use until the end of the MDL.



### -param GpadlHandle [out]

The GPADL handle of the created MDL. Send this to the server to use with the <a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a> function.


## -remarks



When this function returns, the server
endpoint can call <a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a>, because VMBus will already have send
the GPADL description to the opposite endpoint and received confirmation.


 The GPADL must be deleted by using the <a href="https://msdn.microsoft.com/B1446A29-F2C1-4F08-8B38-5BE9188F5132">VmbChannelDeleteGpadl</a> function.




## -see-also




<a href="https://msdn.microsoft.com/B1446A29-F2C1-4F08-8B38-5BE9188F5132">VmbChannelDeleteGpadl</a>



<a href="https://msdn.microsoft.com/A7801EE9-BFDB-4F77-9DA4-A6612F63AD48">VmbChannelMapGpadl</a>
 

 

