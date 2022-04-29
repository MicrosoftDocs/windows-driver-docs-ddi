---
UID: NC:acxelements.EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS
tech.root: audio 
title: EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS
ms.date: 04/29/2022
targetos: Windows
description: EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS assigns detection patterns for keyword detection to be used by the keyword spotter.
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
 - EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS
f1_keywords:
 - EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS
 - acxelements/EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS
dev_langs:
 - c++
---

## -description

The **EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS** callback assigns detection patterns for keyword detection to be used by the keyword spotter.

## -parameters

### -param KeywordSpotter

An existing, initialized, ACXKEYWORDSPOTTER object. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). Also see the [AcxKeywordSpotterCreate](nf-acxelements-acxkeywordspottercreate.md) function.

### -param EventId

A pointer to a GUID that represents the EventId. 

### -param Pattern

A GUID identifying the keyword spotter detection pattern. 

### -param PatternSize

The length, in bytes, of the keyword detection pattern.

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

For general information about keyword detection, see [Voice Activation](/windows-hardware/drivers/audio/voice-activation) and [Multiple Voice Assistant](/windows-hardware/drivers/audio/voice-activation-mva).

### Example

Example usage is shown below.

```cpp
EVT_ACX_KEYWORDSPOTTER_ASSIGN_PATTERNS  CodecC_EvtAcxKeywordSpotterAssignPatterns;

NTSTATUS
NTAPI
CodecC_EvtAcxKeywordSpotterAssignPatterns(
    _In_    ACXKEYWORDSPOTTER   KeywordSpotter,
    _In_    GUID *              EventId,
    _In_    PVOID               Pattern,
    _In_    ULONG               PatternSize
    )
{
    KSMULTIPLE_ITEM *               itemsHeader = nullptr;
    SOUNDDETECTOR_PATTERNHEADER *   patternHeader;
    CONTOSO_KEYWORDCONFIGURATION *  pattern;
    ULONG                           cbRemaining = 0;
    PCODEC_KEYWORDSPOTTER_CONTEXT   keywordSpotterCtx;
    CKeywordDetector *              keywordDetector = NULL;

    PAGED_CODE();

    keywordSpotterCtx = GetCodecKeywordSpotterContext(KeywordSpotter);

    keywordDetector = (CKeywordDetector*)keywordSpotterCtx->KeywordDetector;

    cbRemaining = PatternSize;

    // The SYSVADPROPERTY_ITEM for this property ensures the value size is at
    // least sizeof KSMULTIPLE_ITEM.
    if (cbRemaining < sizeof(KSMULTIPLE_ITEM))
    {
        return STATUS_INVALID_PARAMETER;
    }

    itemsHeader = (KSMULTIPLE_ITEM*)Pattern;

    // Verify property value is large enough to include the items
    if (itemsHeader->Size > cbRemaining)
    {
        return STATUS_INVALID_PARAMETER;
    }

    // No items so clear the configuration.
    if (itemsHeader->Count == 0)
    {
        keywordDetector->ResetDetector(*EventId);
        return STATUS_SUCCESS;
    }

    // This sample supports only 1 pattern type.
    if (itemsHeader->Count > 1)
    {
        return STATUS_NOT_SUPPORTED;
    }

    // Bytes remaining after the items header
    cbRemaining = itemsHeader->Size - sizeof(*itemsHeader);

    // Verify the property value is large enough to include the pattern header.
    if (cbRemaining < sizeof(SOUNDDETECTOR_PATTERNHEADER))
    {
        return STATUS_INVALID_PARAMETER;
    }

    patternHeader = (SOUNDDETECTOR_PATTERNHEADER*)(itemsHeader + 1);

    // Verify the pattern type is supported.
    if (patternHeader->PatternType != CONTOSO_KEYWORDCONFIGURATION_IDENTIFIER2)
    {
        return STATUS_NOT_SUPPORTED;
    }

    // Verify the property value is large enough for the pattern.
    if (cbRemaining < patternHeader->Size)
    {
        return STATUS_INVALID_PARAMETER;
    }

    // Verify the pattern is large enough.
    if (patternHeader->Size != sizeof(CONTOSO_KEYWORDCONFIGURATION))
    {
        return STATUS_INVALID_PARAMETER;
    }

    pattern = (CONTOSO_KEYWORDCONFIGURATION*)(patternHeader);

    return keywordDetector->DownloadDetectorData(*EventId, pattern->ContosoDetectorConfigurationData);
}
```

## -see-also

- [acxelements.h header](index.md)

READY2GO

EDITCOMPLETE