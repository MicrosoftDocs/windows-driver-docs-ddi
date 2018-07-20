---
UID: NS:bthddi._CHANNEL_CONFIG_PARAMETERS_ENHANCED
title: "_CHANNEL_CONFIG_PARAMETERS_ENHANCED"
author: windows-driver-content
description: The CHANNEL_CONFIG_PARAMETERS_ENHANCED structure describes configuration parameters for inbound and outbound directions of an L2CAP channel.
old-location: bltooth\channel_config_parameters_enhanced.htm
tech.root: bltooth
ms.assetid: 4C28FD6E-A1DD-4887-95B0-6028ECA18204
ms.author: windowsdriverdev
ms.date: 4/27/2018
ms.keywords: "*PCHANNEL_CONFIG_PARAMETERS_ENHANCED, CHANNEL_CONFIG_PARAMETERS_ENHANCED, CHANNEL_CONFIG_PARAMETERS_ENHANCED structure [Bluetooth Devices], PCHANNEL_CONFIG_PARAMETERS_ENHANCED, PCHANNEL_CONFIG_PARAMETERS_ENHANCED structure pointer [Bluetooth Devices], _CHANNEL_CONFIG_PARAMETERS_ENHANCED, bltooth.channel_config_parameters_enhanced, bthddi/CHANNEL_CONFIG_PARAMETERS_ENHANCED, bthddi/PCHANNEL_CONFIG_PARAMETERS_ENHANCED"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Bthddi.h
api_name:
-	CHANNEL_CONFIG_PARAMETERS_ENHANCED
product:
- Windows
targetos: Windows
req.typenames: CHANNEL_CONFIG_PARAMETERS_ENHANCED, *PCHANNEL_CONFIG_PARAMETERS_ENHANCED
---

# _CHANNEL_CONFIG_PARAMETERS_ENHANCED structure


## -description


The CHANNEL_CONFIG_PARAMETERS_ENHANCED structure describes configuration parameters for inbound and outbound directions of an L2CAP channel.


## -struct-fields




### -field Flags

Combination of CFG_XXX flags.


### -field Mtu

MTU for the direction.


### -field FlushTO

Flush timeout for the direction


### -field NumExtraOptions

Number of elements in the ExtraOptions array


### -field ExtraOptions

Array of extra options


### -field Flow

QOS for the direction


### -field RetransmissionAndFlow

Retransmission and flow for the direction


### -field Fcs

Frame check sequence


### -field ExtendedFlowSpec

Extended flow specification for the L2CAP channel. This member is reserved. Do not use.


### -field ExtendedWindowSize

Extended window size. This member is reserved. Do not use.

