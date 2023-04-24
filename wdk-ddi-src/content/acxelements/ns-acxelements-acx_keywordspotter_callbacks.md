---
UID: NS:acxelements._ACX_KEYWORDSPOTTER_CALLBACKS
tech.root: audio 
title: ACX_KEYWORDSPOTTER_CALLBACKS
ms.date: 04/29/2022
targetos: Windows
description: The ACX_KEYWORDSPOTTER_CALLBACKS structure identifies the driver callbacks for key word spotter operations.
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
req.typenames: ACX_KEYWORDSPOTTER_CALLBACKS, *PACX_KEYWORDSPOTTER_CALLBACKS
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - _ACX_KEYWORDSPOTTER_CALLBACKS
 - PACX_KEYWORDSPOTTER_CALLBACKS
 - ACX_KEYWORDSPOTTER_CALLBACKS
f1_keywords:
 - _ACX_KEYWORDSPOTTER_CALLBACKS
 - acxelements/_ACX_KEYWORDSPOTTER_CALLBACKS
 - PACX_KEYWORDSPOTTER_CALLBACKS
 - acxelements/PACX_KEYWORDSPOTTER_CALLBACKS
 - ACX_KEYWORDSPOTTER_CALLBACKS
 - acxelements/ACX_KEYWORDSPOTTER_CALLBACKS
dev_langs:
 - c++
---

## -description

The ACX_KEYWORDSPOTTER_CALLBACKS structure identifies the driver callbacks for keyword spotter operations.

## -struct-fields

### -field Size

The length, in bytes, of this callbacks structure.

### -field EvtAcxKeywordSpotterRetrieveArm

The [ACX_KEYWORDSPOTTER_RETRIEVE_ARM](nc-acxelements-evt_acx_keywordspotter_retrieve_arm.md) callback.

### -field EvtAcxKeywordSpotterAssignArm

The [ACX_KEYWORDSPOTTER_ASSIGN_ARM](nc-acxelements-evt_acx_keywordspotter_assign_arm.md) callback.

### -field EvtAcxKeywordSpotterAssignPatterns

The [ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS](nc-acxelements-evt_acx_keywordspotter_assign_patterns.md) callback.

### -field EvtAcxKeywordSpotterAssignReset

The [ACX_KEYWORDSPOTTER_ASSIGN_RESET](nc-acxelements-evt_acx_keywordspotter_assign_reset.md) callback.

## -remarks

### Example

Example usage is shown below.

```cpp
    ACX_KEYWORDSPOTTER_CALLBACKS    keywordSpotterCallbacks;

    ACX_KEYWORDSPOTTER_CALLBACKS_INIT(&keywordSpotterCallbacks);
    keywordSpotterCallbacks.EvtAcxKeywordSpotterRetrieveArm = CodecC_EvtAcxKeywordSpotterRetrieveArm;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignArm = CodecC_EvtAcxKeywordSpotterAssignArm;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignPatterns = CodecC_EvtAcxKeywordSpotterAssignPatterns;
    keywordSpotterCallbacks.EvtAcxKeywordSpotterAssignReset = CodecC_EvtAcxKeywordSpotterAssignReset;
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)
