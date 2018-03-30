---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelMapGpadl
title: VmbChannelMapGpadl function
author: windows-driver-content
description: The VmbChannelMapGpadl function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number.
old-location: netvista\vmbchannelmapgpadl.htm
old-project: netvista
ms.assetid: A7801EE9-BFDB-4F77-9DA4-A6612F63AD48
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY, VmbChannelMapGpadl, VmbChannelMapGpadl function [Network Drivers Starting with Windows Vista], netvista.vmbchannelmapgpadl, vmbuskernelmodeclientlibapi/VmbChannelMapGpadl
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
req.lib: 
req.dll: 
req.irql: 
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	VmbusKernelModeClientLibApi.h
api_name:
-	VmbChannelMapGpadl
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelMapGpadl function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelMapGpadl</b>  function maps a client-side buffer into server-side physical address space by using a Guest Physical Address Descriptor List (GPADL) number. 


## -parameters




### -param Channel [in]

A handle for a channel.  


### -param Flags [in]

Flags.  The possible flag values are:

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td width="40%"><a id="VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY"></a><a id="vmbus_channel_gpadl_flag_read_only"></a><dl>
<dt><b>VMBUS_CHANNEL_GPADL_FLAG_READ_ONLY</b></dt>
</dl>
</td>
<td width="60%">
Map with read-only access. 

</td>
</tr>
</table>
 

If
this flag value is not set, the function tries to map the GPADL for write access. If the GPADL was not
created with write access, this mapping attempt fails. The
caller is not prevented from writing to the buffer if this flag is set. This scheme is used to improve the performance of live migration
and snapshotting.



### -param GpadlHandle [in]

The GPADL handle of the GPADL to map.



### -param Mdl [out]

 A pointer to a MDL describing the client buffer. This
buffer is only mapped into physical address space. The caller must take
additional steps to map it into virtual address space.


## -remarks



The GPADL must have been pre-established by the client, for instance, by using the <a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a> function.  

Only a single mapping may exist for any given GPADL at a time.  

You must pair calls to this
function with calls to the <a href="https://msdn.microsoft.com/EE300158-D7D8-4353-B205-362232A22568">VmbChannelUnmapGpadl</a> function.




## -see-also




<a href="https://msdn.microsoft.com/B45E2463-1EBC-4F32-B3AD-8331E664BB24">VmbChannelCreateGpadlFromBuffer</a>



<a href="https://msdn.microsoft.com/EE300158-D7D8-4353-B205-362232A22568">VmbChannelUnmapGpadl</a>
 

 

<<<<<<< HEAD
=======
<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20VmbChannelMapGpadl function%20 RELEASE:%20(2/27/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

>>>>>>> parent of 2d896a8e266... Added changes
