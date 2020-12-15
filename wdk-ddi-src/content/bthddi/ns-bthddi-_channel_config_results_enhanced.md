---
UID: NS:bthddi._CHANNEL_CONFIG_RESULTS_ENHANCED
title: _CHANNEL_CONFIG_RESULTS_ENHANCED (bthddi.h)
description: The CHANNEL_CONFIG_RESULTS_ENHANCED structure describes configuration parameters and the buffer size of any extra option for the inbound and outbound directions of an L2CAP channel.
old-location: bltooth\channel_config_results_enhanced.htm
tech.root: bltooth
ms.date: 04/27/2018
keywords: ["CHANNEL_CONFIG_RESULTS_ENHANCED structure"]
ms.keywords: "*PCHANNEL_CONFIG_RESULTS_ENHANCED, CHANNEL_CONFIG_RESULTS_ENHANCED, CHANNEL_CONFIG_RESULTS_ENHANCED structure [Bluetooth Devices], PCHANNEL_CONFIG_RESULTS_ENHANCED, PCHANNEL_CONFIG_RESULTS_ENHANCED structure pointer [Bluetooth Devices], _CHANNEL_CONFIG_RESULTS_ENHANCED, bltooth.channel_config_results_enhanced, bthddi/CHANNEL_CONFIG_RESULTS_ENHANCED, bthddi/PCHANNEL_CONFIG_RESULTS_ENHANCED"
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows 8 and later versions of Windows
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
req.typenames: CHANNEL_CONFIG_RESULTS_ENHANCED, *PCHANNEL_CONFIG_RESULTS_ENHANCED
f1_keywords:
 - _CHANNEL_CONFIG_RESULTS_ENHANCED
 - bthddi/_CHANNEL_CONFIG_RESULTS_ENHANCED
 - PCHANNEL_CONFIG_RESULTS_ENHANCED
 - bthddi/PCHANNEL_CONFIG_RESULTS_ENHANCED
 - CHANNEL_CONFIG_RESULTS_ENHANCED
 - bthddi/CHANNEL_CONFIG_RESULTS_ENHANCED
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Bthddi.h
api_name:
 - CHANNEL_CONFIG_RESULTS_ENHANCED
---

# _CHANNEL_CONFIG_RESULTS_ENHANCED structure


## -description

The CHANNEL_CONFIG_RESULTS_ENHANCED structure describes configuration parameters and the buffer size of any extra option for the inbound and outbound directions of an L2CAP channel.

## -struct-fields

### -field Params

Channel parameters for the given direction of the channel

### -field ExtraOptionsBufferSize

Amount of buffer required to retrieve the current extra options for the given direction

