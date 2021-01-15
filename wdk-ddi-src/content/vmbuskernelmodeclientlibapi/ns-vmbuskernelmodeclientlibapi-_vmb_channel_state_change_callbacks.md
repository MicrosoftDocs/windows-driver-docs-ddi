---
UID: NS:vmbuskernelmodeclientlibapi._VMB_CHANNEL_STATE_CHANGE_CALLBACKS
title: _VMB_CHANNEL_STATE_CHANGE_CALLBACKS (vmbuskernelmodeclientlibapi.h)
description: The VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure contains callback functions that relate to the state changes for a channel.
old-location: netvista\vmb_channel_state_change_callbacks.htm
tech.root: netvista
ms.date: 05/02/2018
keywords: ["VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure"]
ms.keywords: "*PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, PVMB_CHANNEL_STATE_CHANGE_CALLBACKS structure pointer [Network Drivers Starting with Windows Vista], VMB_CHANNEL_STATE_CHANGE_CALLBACKS, VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure [Network Drivers Starting with Windows Vista], _VMB_CHANNEL_STATE_CHANGE_CALLBACKS, netvista.vmb_channel_state_change_callbacks, vmbuskernelmodeclientlibapi/PVMB_CHANNEL_STATE_CHANGE_CALLBACKS, vmbuskernelmodeclientlibapi/VMB_CHANNEL_STATE_CHANGE_CALLBACKS"
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: VMB_CHANNEL_STATE_CHANGE_CALLBACKS, *PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
f1_keywords:
 - _VMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - vmbuskernelmodeclientlibapi/_VMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - vmbuskernelmodeclientlibapi/PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - VMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - vmbuskernelmodeclientlibapi/VMB_CHANNEL_STATE_CHANGE_CALLBACKS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - VmbusKernelModeClientLibApi.h
api_name:
 - _VMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - PVMB_CHANNEL_STATE_CHANGE_CALLBACKS
 - VMB_CHANNEL_STATE_CHANGE_CALLBACKS
---

# _VMB_CHANNEL_STATE_CHANGE_CALLBACKS structure


## -description

<p class="CCE_Message">[Some information relates to pre-released product which may be substantially modified before it's commercially released. Microsoft makes no warranties, express or implied, with respect to the information provided here.]

The <b>VMB_CHANNEL_STATE_CHANGE_CALLBACKS</b> structure contains callback functions that relate to the state changes for a channel.

## -struct-fields

### -field Version

The version.

### -field Size

Size of callbacks.

### -field EvtChannelOpened

The channel opened callback function.

### -field EvtChannelClosed

The channel closed callback function.

### -field EvtChannelSuspend

The channel suspended callback function.

### -field EvtChannelStarted

The channel started callback function.

### -field EvtChannelPostStarted

The channel post started callback function.

