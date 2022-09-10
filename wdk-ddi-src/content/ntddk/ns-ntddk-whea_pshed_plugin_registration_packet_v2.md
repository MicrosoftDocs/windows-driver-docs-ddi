---
UID: NS:ntddk._WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
title: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
description: "Learn more about: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2 structure"
tech.root: whea
ms.date: 08/19/2019
keywords: ["WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2 structure"]
ms.keywords: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2, WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2, WHEA_PSHED_PLUGIN_REGISTRATION_PACKET, *PWHEA_PSHED_PLUGIN_REGISTRATION_PACKET
req.header: ntddk.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.ddi-compliance: 
req.unicode-ansi: 
req.max-support: 
req.typenames: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
 - ntddk/_WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
 - WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
 - ntddk/WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
 - WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2
product:
 - Windows
---

# WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2 structure


## -description

Reserved for system use.
The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V2 structure describes the data required for registering a PSHED plug-in with the PSHED.

## -struct-fields

### -field Length

The size, in bytes, of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure.

### -field Version

The version of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure. PSHED plug-ins must set this member to WHEA_PLUGIN_REGISTRATION_PACKET_VERSION, which will be set to the default WHEA_PLUGIN_REGISTRATION_PACKET_V2.

### -field Context

A PSHED plug-in-supplied context area that is passed to the PSHED plug-in's callback functions.

### -field FunctionalAreaMask

A bit-wise OR'ed combination of flags that specifies the functional areas in which the PSHED plug-in participates. Possible flags are:

### -field Reserved

Reserved for system use. PSHED plug-ins should set this member to zero.

### -field Callbacks

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_callbacks">WHEA_PSHED_PLUGIN_CALLBACKS</a> structure that describes the callback functions for the PSHED plug-in.

### -field PluginHandle

V2 plugins can be unregistered via the PluginHandle. Save this for unregistering. Only V2 plugins have the ability to be unregistered.

## -remarks

V2 plugins are the default. If you are creating a new PSHED plugin, create a V2 plugin.

## -see-also

