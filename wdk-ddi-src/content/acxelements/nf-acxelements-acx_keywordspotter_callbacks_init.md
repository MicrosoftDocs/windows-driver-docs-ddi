---
UID: NF:acxelements.ACX_KEYWORDSPOTTER_CALLBACKS_INIT
tech.root: audio 
title: ACX_KEYWORDSPOTTER_CALLBACKS_INIT
ms.date: 04/05/2022
targetos: Windows
description: The ACX_KEYWORDSPOTTER_CALLBACKS_INIT function initializes a ACX_KEYWORDSPOTTER_CALLBACKS structure. 
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxelements.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxelements.h
api_name:
 - ACX_KEYWORDSPOTTER_CALLBACKS_INIT
f1_keywords:
 - ACX_KEYWORDSPOTTER_CALLBACKS_INIT
 - acxelements/ACX_KEYWORDSPOTTER_CALLBACKS_INIT
dev_langs:
 - c++
---

## -description

The ACX_KEYWORDSPOTTER_CALLBACKS_INIT function initializes a [ACX_KEYWORDSPOTTER_CALLBACKS structure](ns-acxelements-acx_keywordspotter_callbacks.md). 

## -parameters

### -param Callbacks

A pointer to an initialized [ACX_KEYWORDSPOTTER_CALLBACKS structure](ns-acxelements-acx_keywordspotter_callbacks.md). 

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

- [acxelements.h header](index.md)

READY2GO

EDITCOMPLETE