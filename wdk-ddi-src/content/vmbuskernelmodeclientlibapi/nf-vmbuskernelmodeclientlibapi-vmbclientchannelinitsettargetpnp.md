---
UID: NF:vmbuskernelmodeclientlibapi.VmbClientChannelInitSetTargetPnp
title: VmbClientChannelInitSetTargetPnp function
author: windows-driver-content
description: The VmbClientChannelInitSetTargetPnp function sets a client channel's target by interface type and instance IDs.
old-location: netvista\vmbclientchannelinitsettargetpnp.htm
old-project: netvista
ms.assetid: 5525FD48-BE65-48CA-B3D5-C96AFD4ECF56
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: VmbClientChannelInitSetTargetPnp, VmbClientChannelInitSetTargetPnp function [Network Drivers Starting with Windows Vista], netvista.vmbclientchannelinitsettargetpnp, vmbuskernelmodeclientlibapi/VmbClientChannelInitSetTargetPnp
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
-	VmbClientChannelInitSetTargetPnp
product:
- Windows
targetos: Windows
req.typenames: 
---

# VmbClientChannelInitSetTargetPnp function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbClientChannelInitSetTargetPnp</b> function sets a client channel's target by interface type and instance IDs. If this
function is called, Kernel Mode Client Library (KMCL) uses PnP to find the VMBus Physical Device Object (PDO) that corresponds to the
provided interface. 


## -parameters




### -param Channel [in]

A pointer to a channel.



### -param InterfaceType [in]

A pointer to the interface type GUID.
This GUID identifies the 
type of channel and the protocol that is used with the channel.  


### -param InterfaceInstance [in, optional]

A pointer to the instance type GUID. This is a 
specific instance of the service. If not
provided, any instance with the provided type is accepted.



### -param PnpFailureCallback [in, optional]

A pointer to an event callback to call if the
device asynchronously fails to connect even though the PnP device was
located.


## -returns



<b>VmbClientChannelInitSetTargetPnp</b> returns the following values: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER_1</b></dt>
</dl>
</td>
<td width="60%">
The <i>Channel</i> value was invalid or in an invalid state, such as Disabled.

</td>
</tr>
</table>
 




## -remarks



If you 
have two paravirtual network interfaces, they will have the 
same <i>InterfaceType</i> but different <i>InterfaceInstance</i> values. 



