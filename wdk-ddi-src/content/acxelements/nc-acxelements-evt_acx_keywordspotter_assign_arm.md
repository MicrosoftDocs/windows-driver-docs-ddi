---
UID: NC:acxelements.EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM
tech.root: audio 
title: EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM
ms.date: 04/29/2022
targetos: Windows
description: EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM sets the arm state of the keyword spotter.
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
 - EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM
f1_keywords:
 - EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM
 - acxelements/EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM
dev_langs:
 - c++
---

## -description

The **EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM** callback sets the arm state of the keyword spotter.

## -parameters

### -param KeywordSpotter

An existing, initialized, ACXKEYWORDSPOTTER object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). Also see the [AcxKeywordSpotterCreate](nf-acxelements-acxkeywordspottercreate.md) function.

### -param EventId

A pointer to a GUID that represents the EventId. 

### -param Arm

A boolean value indicating if the keyword detection is armed.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

For general information about keyword detection, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation) and [Multiple Voice Assistant](/windows-hardware/drivers/audio/voice-activation-mva).

### Example

Example usage is shown below.

```cpp
EVT_ACX_KEYWORDSPOTTER_ASSIGN_ARM       DspC_EvtAcxKeywordSpotterAssignArm;

PAGED_CODE_SEG
NTSTATUS DspC_EvtAcxKeywordSpotterAssignArm(
    _In_    ACXKEYWORDSPOTTER   KeywordSpotter,
    _In_    GUID *              EventId,
    _In_    BOOLEAN             Arm
)
{
    PAGED_CODE();
    PDSP_KEYWORDSPOTTER_CONTEXT     keywordSpotterCtx;
    CKeywordDetector *              keywordDetector = NULL;

    keywordSpotterCtx = GetDspKeywordSpotterContext(KeywordSpotter);

    keywordDetector = (CKeywordDetector*)keywordSpotterCtx->KeywordDetector;

    RETURN_NTSTATUS_IF_FAILED(keywordDetector->SetArmed(*EventId, Arm));

    // the following code is for example only, after arming the
    // requested keyword we immediately trigger a detection
    // so that the automated tests do not block.
    if (Arm)
    {
        CONTOSO_KEYWORDDETECTIONRESULT detectionResult;

        // notify the keyword detector that we have a notification, to populate
        // timestamp information for this detection.
        keywordDetector->NotifyDetection();

        // fill in the detection specific information
        detectionResult.EventId = *EventId;
        detectionResult.Header.Size = sizeof(CONTOSO_KEYWORDDETECTIONRESULT);
        detectionResult.Header.PatternType = CONTOSO_KEYWORDCONFIGURATION_IDENTIFIER2;
        detectionResult.KeywordStartTimestamp = keywordDetector->GetStartTimestamp();
        detectionResult.KeywordStopTimestamp = keywordDetector->GetStopTimestamp();
        keywordDetector->GetDetectorData(*EventId, &(detectionResult.ContosoDetectorResultData));

        RETURN_NTSTATUS_IF_FAILED(AcxPnpEventGenerateEvent(keywordSpotterCtx->Event, &detectionResult, sizeof(CONTOSO_KEYWORDDETECTIONRESULT)));
    }

    return STATUS_SUCCESS;
}
```

## -see-also

- [acxelements.h header](index.md)
