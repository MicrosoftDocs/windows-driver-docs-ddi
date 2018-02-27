---
UID: NF:vmbuskernelmodeclientlibapi.VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT
title: VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT function
author: windows-driver-content
description: The VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT function saves callback functions to be used for state changes for a channel.
old-location: netvista\vmb_channel_state_change_callbacks_init.htm
old-project: netvista
ms.assetid: 2255C8A2-85FB-4B96-8AE9-66FAFD73EE73
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT, VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT function [Network Drivers Starting with Windows Vista], netvista.vmb_channel_state_change_callbacks_init, vmbuskernelmodeclientlibapi/VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: vmbuskernelmodeclientlibapi.h
req.include-header: VmbusKernelModeClientLibApi.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
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
-	VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT
product: Windows
targetos: Windows
req.typenames: VIDEO_PORT_AGP_SERVICES, *PVIDEO_PORT_AGP_SERVICES
req.product: Windows 10 or later.
---

# VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT function


## -description


<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT</b> function saves callback functions to be used for state changes for a channel. 


## -syntax


````
VOID WINAPI VMB_CHANNEL_STATE_CHANGE_CALLBACKS_INIT(
  _Out_ PVMB_CHANNEL_STATE_CHANGE_CALLBACKS Callbacks
);
````


## -parameters




### -param Callbacks [out]

A structure to save callback functions that relate to the state changes for a channel. 


## -returns



This function does not return a value.



