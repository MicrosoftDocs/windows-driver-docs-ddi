---
UID: NS:acxelements._ACX_KEYWORDSPOTTER_CONFIG
tech.root: audio 
title: ACX_KEYWORDSPOTTER_CONFIG
ms.date: 04/29/2022
targetos: Windows
description: The ACX_KEYWORDSPOTTER_CONFIG structure is used to define the audio keyword spotter configuration. 
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_KEYWORDSPOTTER_CONFIG, *PACX_KEYWORDSPOTTER_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_KEYWORDSPOTTER_CONFIG
 - PACX_KEYWORDSPOTTER_CONFIG
 - ACX_KEYWORDSPOTTER_CONFIG
f1_keywords:
 - _ACX_KEYWORDSPOTTER_CONFIG
 - acxelements/_ACX_KEYWORDSPOTTER_CONFIG
 - PACX_KEYWORDSPOTTER_CONFIG
 - acxelements/PACX_KEYWORDSPOTTER_CONFIG
 - ACX_KEYWORDSPOTTER_CONFIG
 - acxelements/ACX_KEYWORDSPOTTER_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_KEYWORDSPOTTER_CONFIG** structure is used to define the acx keyword spotter configuration. 

## -struct-fields

### -field Size

The length, in bytes, of this structure.

### -field Id

A number that represents the element ID.

### -field Name

A pointer to a GUID that represents the name of the element. Can be used for debugging and will default to GUID_NULL if not provided.

### -field Flags

Acx keyword spotter configuration flags defined by the [ACX_KEYWORDSPOTTER_CONFIG_FLAGS enum](ne-acxelements-acx_keywordspotter_config_flags.md). No flag bits are currently defined. Set this member to zero - AcxKeywordSpotterConfigNoFlags.

### -field Pattern

The keyword spotter pattern format, expressed as a GUID.

### -field Callbacks

The [ACX_KEYWORDSPOTTER_CALLBACKS structure](ns-acxelements-acx_keywordspotter_callbacks.md) that identifies the driver callbacks for the keyword spotter operations.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_KEYWORDSPOTTER_CONFIG       keywordSpotterCfg;
    PCODEC_KEYWORDSPOTTER_CONTEXT   keywordSpotterCtx;
    ACX_PNPEVENT_CONFIG             keywordEventCfg;
    ACXPNPEVENT                     keywordEvent;

    ACX_KEYWORDSPOTTER_CALLBACKS_INIT(&keywordSpotterCallbacks);
    keywordSpotterCallbacks.EvtAcxKeywordSpotterRetrieveArm = CodecC_EvtAcxKeywordSpotterRetrieveArm;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignArm = CodecC_EvtAcxKeywordSpotterAssignArm;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignPatterns = CodecC_EvtAcxKeywordSpotterAssignPatterns;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignReset = CodecC_EvtAcxKeywordSpotterAssignReset;
    
    ACX_KEYWORDSPOTTER_CONFIG_INIT(&keywordSpotterCfg);
    keywordSpotterCfg.Pattern = &CONTOSO_KEYWORDCONFIGURATION_IDENTIFIER2;
    keywordSpotterCfg.Callbacks = &keywordSpotterCallbacks;
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
