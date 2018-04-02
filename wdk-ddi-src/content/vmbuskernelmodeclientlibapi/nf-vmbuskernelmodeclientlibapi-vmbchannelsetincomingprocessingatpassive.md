---
UID: NF:vmbuskernelmodeclientlibapi.VmbChannelSetIncomingProcessingAtPassive
title: VmbChannelSetIncomingProcessingAtPassive function
author: windows-driver-content
description: The VmbChannelSetIncomingProcessingAtPassive function sets the required IRQL for incoming parsing routines for a channel to PASSIVE_LEVEL.
old-location: netvista\vmbchannelsetincomingprocessingatpassive.htm
old-project: netvista
ms.assetid: D8677CD9-46CB-41AB-8F05-418A31468C07
ms.author: windowsdriverdev
ms.date: 3/26/2018
ms.keywords: VmbChannelSetIncomingProcessingAtPassive, VmbChannelSetIncomingProcessingAtPassive function [Network Drivers Starting with Windows Vista], netvista.vmbchannelsetincomingprocessingatpassive, vmbuskernelmodeclientlibapi/VmbChannelSetIncomingProcessingAtPassive
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
-	VmbChannelSetIncomingProcessingAtPassive
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VmbChannelSetIncomingProcessingAtPassive function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VmbChannelSetIncomingProcessingAtPassive</b> function sets the required IRQL for incoming parsing routines for a channel to
PASSIVE_LEVEL.


## -parameters




### -param Channel [in]

A handle for a channel.  



### -param RequirePassive [in]

If true, the channel requires PASSIVE_LEVEL. If false, packets may arrive at either DISPATCH_LEVEL or PASSIVE_LEVEL.


## -returns



This function does not return a value.



