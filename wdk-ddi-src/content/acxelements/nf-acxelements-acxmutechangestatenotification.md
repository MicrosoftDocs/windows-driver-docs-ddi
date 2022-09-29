---
UID: NF:acxelements.AcxMuteChangeStateNotification
tech.root: audio 
title: AcxMuteChangeStateNotification
ms.date: 04/29/2022
targetos: Windows
description: The AcxMuteChangeStateNotification function sends a notification of a mute state change on an ACXMUTE object so that acx can generate a corresponding event. 
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
 - AcxMuteChangeStateNotification
f1_keywords:
 - AcxMuteChangeStateNotification
 - acxelements/AcxMuteChangeStateNotification
dev_langs:
 - c++
---

## -description

The **AcxMuteChangeStateNotification** function sends a notification of a mute state change on an ACXMUTE object so that acx can generate a corresponding event. 

## -parameters

### -param Mute

An ACXMUTE object whose mute state has changed. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

## -remarks

### Example

Example usage is shown below.

```cpp
    PCODEC_MUTE_TIMER_CONTEXT timerCtx = GetCodecMuteTimerContext(Timer);
    PCODEC_MUTE_ELEMENT_CONTEXT muteCtx = GetCodecMuteElementContext(timerCtx->MuteElement);

    // update settings 0 <-> 1 
    for (ULONG i = 0; i < MAX_CHANNELS; ++i)
    {
        muteCtx->MuteState[i] = !muteCtx->MuteState[i];
    }

    AcxMuteChangeStateNotification(timerCtx->MuteElement);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


