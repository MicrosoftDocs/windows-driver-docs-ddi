---
UID: NS:ntddk._WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
title: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
description: "Learn more about: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1 structure"
tech.root: whea
ms.date: 08/19/2019
keywords: ["WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1 structure"]
ms.keywords: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1, WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1,
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
req.typenames: WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
targetos: Windows
ms.custom: 19H1
f1_keywords:
 - _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
 - ntddk/_WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
 - WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
 - ntddk/WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
 - WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1
product:
 - Windows
---

# WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1 structure


## -description

Reserved for system use.
The WHEA_PSHED_PLUGIN_REGISTRATION_PACKET_V1 structure describes the data required for registering a PSHED plug-in with the PSHED.

## -struct-fields

### -field Length

### -field Version

The version of the WHEA_PSHED_PLUGIN_REGISTRATION_PACKET structure. PSHED plug-ins must set this member to WHEA_PLUGIN_REGISTRATION_PACKET_VERSION.

### -field Context

A PSHED plug-in-supplied context area that is passed to the PSHED plug-in's callback functions.

### -field FunctionalAreaMask

A bit-wise OR'ed combination of flags that specifies the functional areas in which the PSHED plug-in participates. Possible flags are:

### -field Reserved

Reserved for system use. PSHED plug-ins should set this member to zero.

### -field Callbacks

A <a href="/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_whea_pshed_plugin_callbacks">WHEA_PSHED_PLUGIN_CALLBACKS</a> structure that describes the callback functions for the PSHED plug-in.

## -remarks

## -see-also

