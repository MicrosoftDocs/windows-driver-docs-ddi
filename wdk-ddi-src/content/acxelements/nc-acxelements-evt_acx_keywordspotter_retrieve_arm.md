---
UID: NC:acxelements.EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM
tech.root: audio 
title: EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM
ms.date: 09/15/2021
targetos: Windows
description: TBD - EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM tells the driver to that the keyword spotter (?? TBD has ) that the arm status has been or is being??? requested???.
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
 - EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM
f1_keywords:
 - EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM
 - acxelements/EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM tells the driver to that the keyword spotter (?? TBD has ) that the arm status has been or is being??? requested???.

## -parameters

### -param KeywordSpotter

An existing, initialized, ACXKEYWORDSPOTTER object.    For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). Also see the [AcxKeywordSpotterCreate](nf-acxelements-acxkeywordspottercreate.md) function.

### -param EventId

A pointer to a GUID that represents the EventId. 

### -param Arm

A boolean value indicating if the keyword detection is armed (TBD - will be armed).

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

For general information about keyword detection, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation) and [Multiple Voice Assistant](/windows-hardware/drivers/audio/voice-activation-mva).

### Example

Example usage is shown below.

```cpp
EVT_ACX_KEYWORDSPOTTER_RETRIEVE_ARM     CodecC_EvtAcxKeywordSpotterRetrieveArm;

NTSTATUS
NTAPI
CodecC_EvtAcxKeywordSpotterRetrieveArm(
    _In_    ACXKEYWORDSPOTTER   KeywordSpotter,
    _In_    GUID *              EventId,
    _Out_   BOOLEAN *           Arm
    )
{
    PAGED_CODE();
    PCODEC_KEYWORDSPOTTER_CONTEXT keywordSpotterCtx;
    CKeywordDetector *              keywordDetector = NULL;

    keywordSpotterCtx = GetCodecKeywordSpotterContext(KeywordSpotter);

    keywordDetector = (CKeywordDetector*)keywordSpotterCtx->KeywordDetector;

    return keywordDetector->GetArmed(*EventId, Arm);
}
```

## -see-also

[acxelements.h header](index.md)

