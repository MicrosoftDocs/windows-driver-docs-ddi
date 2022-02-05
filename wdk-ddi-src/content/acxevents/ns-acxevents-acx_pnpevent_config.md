---
UID: NS:acxevents._ACX_PNPEVENT_CONFIG
tech.root: audio
title: ACX_PNPEVENT_CONFIG
ms.date: 11/03/2021
targetos: Windows
description: The ACX_PNPEVENT_CONFIG structure is used to define the pnp event configuration. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxevents.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_PNPEVENT_CONFIG, *PACX_PNPEVENT_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxevents.h
api_name:
 - _ACX_PNPEVENT_CONFIG
 - PACX_PNPEVENT_CONFIG
 - ACX_PNPEVENT_CONFIG
f1_keywords:
 - _ACX_PNPEVENT_CONFIG
 - acxevents/_ACX_PNPEVENT_CONFIG
 - PACX_PNPEVENT_CONFIG
 - acxevents/PACX_PNPEVENT_CONFIG
 - ACX_PNPEVENT_CONFIG
 - acxevents/ACX_PNPEVENT_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_PNPEVENT_CONFIG** structure is used to define the ACX pnp event configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure. 

### -field Flags

Bitwise OR of [ACX_PNPEVENT_CONFIG_FLAGS](ne-acxevents-acx_pnpevent_config_flags.md). 

### -field Event

TBD - A GUID that is used to TBD the event.

## -remarks

### Example

This example shows the use of the ACX_PNPEVENT_CONFIG structure.

```cpp
    ACX_PNPEVENT_CONFIG             audioModuleEventCfg;
...

    ACX_PNPEVENT_CONFIG_INIT(&audioModuleEventCfg);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_PNPEVENT_CONTEXT);
    attributes.ParentObject = audioModuleElement;
    status = AcxPnpEventCreate(Device, audioModuleElement, &attributes, &audioModuleEventCfg, &audioModuleEvent);
```

## -see-also

[acxcircuit.h header](index.md)


