---
UID: NC:acxelements.EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET
tech.root: audio 
title: EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET
ms.date: 10/15/2021
targetos: Windows
description: EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET resets the keyword spotter detector to an unarmed state with no pattern set.
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
 - LibDef
api_location:
 - acxelements.h
api_name:
 - EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET
f1_keywords:
 - EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET
 - acxelements/EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET
dev_langs:
 - c++
---

## -description

EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET resets the keyword spotter detector to an unarmed state with no pattern set. 

## -parameters

### -param KeywordSpotter

An existing, initialized, ACXKEYWORDSPOTTER object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). Also see the [AcxKeywordSpotterCreate](nf-acxelements-acxkeywordspottercreate.md) function.

### -param EventId

A pointer to a GUID that represents the EventId. 

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

For general information about keyword detection, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation) and [Multiple Voice Assistant](/windows-hardware/drivers/audio/voice-activation-mva).

### Example

Example usage is shown below.

```cpp
EVT_ACX_KEYWORDSPOTTER_ASSIGN_RESET     CodecC_EvtAcxKeywordSpotterAssignReset;

NTSTATUS
NTAPI
CodecC_EvtAcxKeywordSpotterAssignReset(
    _In_    ACXKEYWORDSPOTTER   KeywordSpotter,
    _In_    GUID *              EventId
    )
{
    PAGED_CODE();
    PCODEC_KEYWORDSPOTTER_CONTEXT keywordSpotterCtx;
    CKeywordDetector *            keywordDetector = NULL;

    keywordSpotterCtx = GetCodecKeywordSpotterContext(KeywordSpotter);

    keywordDetector = (CKeywordDetector*)keywordSpotterCtx->KeywordDetector;

    return keywordDetector->ResetDetector(*EventId);
}
```
READY2GO

## -see-also

[acxelements.h header](index.md)

