---
UID: NC:acxelements.EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
tech.root: audio 
title: EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
ms.date: 09/20/2021
targetos: Windows
description: TBD - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION tells the driver that a request to assign loop back protection has been made???.
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
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
f1_keywords:
 - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
 - acxelements/EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION
dev_langs:
 - c++
---

## -description

TBD - EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION tells the driver that a request to assign loop back protection has been made???.

## -parameters

### -param StreamAudioEngine

An ACXSTREAMAUDIOENGINE ACX audio engine object  that is used in a render circuit, to represent a DSP. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

### -param ConstrictorOption

## -returns

Returns `STATUS_SUCCESS` if the call was successful. Otherwise, it returns an appropriate error code. For more information, see [Using NTSTATUS Values](/windows-hardware/drivers/kernel/using-ntstatus-values).

## -remarks

### Example

Example usage is shown below.

TBD - No call back implementation code found.

```cpp
EVT_ACX_STREAMAUDIOENGINE_ASSIGN_LOOPBACK_PROTECTION        CodecR_EvtAcxStreamAudioEngineAssignLoopbackProtection;

NTSTATUS
CodecR_EvtAcxStreamAudioEngineAssignLoopbackProtection(
    _In_    ACXSTREAMAUDIOENGINE    StreamAudioEngine,
    _In_    ACX_CONSTRICTOR_OPTION  ConstrictorOption
)
{
    UNREFERENCED_PARAMETER(StreamAudioEngine);
    UNREFERENCED_PARAMETER(ConstrictorOption);

    PAGED_CODE();

    return STATUS_SUCCESS;
}

```

## -see-also

[acxelements.h header](index.md)

