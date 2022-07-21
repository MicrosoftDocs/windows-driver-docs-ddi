---
UID: NS:acxevents._ACX_PNPEVENT_CONFIG
tech.root: audio
title: ACX_PNPEVENT_CONFIG
ms.date: 06/22/2022
targetos: Windows
description: The ACX_PNPEVENT_CONFIG structure is used to configure an ACXPNPEVENT. 
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

The **ACX_PNPEVENT_CONFIG** structure is used to configure an ACXPNPEVENT. 

## -struct-fields

### -field Size

The length, in bytes, of this structure. 

### -field Flags

Bitwise OR of [ACX_PNPEVENT_CONFIG_FLAGS](ne-acxevents-acx_pnpevent_config_flags.md).

### -field Event

A GUID that is used to identify the event.

## -remarks

The Event GUID is automatically retrieved from the ACXAUDIOMODULE and ACXKEYWORDSPOTTER when the event is associated with these two types of objects. 

### Example

This example shows the use of the ACX_PNPEVENT_CONFIG structure.

```cpp
    ACX_PNPEVENT_CONFIG audioModuleEventCfg;
...

    ACX_PNPEVENT_CONFIG_INIT(&audioModuleEventCfg);

    WDF_OBJECT_ATTRIBUTES_INIT_CONTEXT_TYPE(&attributes, CODEC_PNPEVENT_CONTEXT);
    attributes.ParentObject = audioModuleElement;
    status = AcxPnpEventCreate(Device, audioModuleElement, &attributes, &audioModuleEventCfg, &audioModuleEvent);
```

## -see-also

- [acxevents.h header](index.md)

READY2GO

EDITCOMPLETE
