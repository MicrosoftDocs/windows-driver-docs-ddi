---
UID: NF:vmbuskernelmodeclientlibapi.VmbServerChannelInitSetTargetInterfaceId
title: VmbServerChannelInitSetTargetInterfaceId function
author: windows-driver-content
description: The VmbServerChannelInitSetTargetInterfaceId function sets the target interface type GUID and instance GUID of the channel offer.
old-location: netvista\vmbserverchannelinitsettargetinterfaceid.htm
old-project: netvista
ms.assetid: 09123845-F734-48B6-A593-0368CD195379
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbServerChannelInitSetTargetInterfaceId, VmbServerChannelInitSetTargetInterfaceId function [Network Drivers Starting with Windows Vista], netvista.vmbserverchannelinitsettargetinterfaceid, vmbuskernelmodeclientlibapi/VmbServerChannelInitSetTargetInterfaceId
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
-	VmbServerChannelInitSetTargetInterfaceId
product:
- Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbServerChannelInitSetTargetInterfaceId function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbServerChannelInitSetTargetInterfaceId</b> function sets the target interface type GUID and instance GUID of the channel offer.  


## -parameters




### -param Channel [in]

A handle for a channel.  


### -param InterfaceType [in]

A pointer to the interface type GUID.



### -param InterfaceInstance [in]

A pointer to the instance type GUID.


## -remarks



The <i>InterfaceType</i>
GUID identifies the type of channel and, specifically, the protocol that is used with
the channel.  If the VMBus in the child partition is creating a Physical Device Object
(PDO) that is associated with this channel, this GUID is the basis of the PDO's hardware
ID reported to the PnP Manager.  

The <i>InterfaceInstance</i> GUID identifies a specific instance
of the service.  For instance, If you have two paravirtual network interfaces, they
have the same interface type, but different interface instance values. 



