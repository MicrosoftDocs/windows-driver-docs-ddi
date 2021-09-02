---
UID: NS:acxelements._ACX_KEYWORDSPOTTER_CALLBACKS
tech.root: audio 
title: ACX_KEYWORDSPOTTER_CALLBACKS
ms.date: 08/27/2021
targetos: Windows
description: 
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

## -struct-fields

### -field Size

TBD - The length, in bytes, of this callbacks structure.

### -field EvtAcxKeywordSpotterRetrieveArm

nc-acxelements-evt_acx_keywordspotter_retrieve_arm.md

### -field EvtAcxKeywordSpotterAssignArm

### -field EvtAcxKeywordSpotterAssignPatterns

### -field EvtAcxKeywordSpotterAssignReset

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

## -see-also

[acxelements.h header](index.md)

