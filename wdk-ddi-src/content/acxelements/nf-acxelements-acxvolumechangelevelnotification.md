---
UID: NF:acxelements.AcxVolumeChangeLevelNotification
tech.root: audio 
title: AcxVolumeChangeLevelNotification
ms.date: 04/29/2022
targetos: Windows
description: The AcxVolumeChangeLevelNotification function sends a notification of a volume level change on an ACXVOLUME object so that acx can generate a corresponding event.
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
 - AcxVolumeChangeLevelNotification
f1_keywords:
 - AcxVolumeChangeLevelNotification
 - acxelements/AcxVolumeChangeLevelNotification
dev_langs:
 - c++
---

## -description

The **AcxVolumeChangeLevelNotification** function sends a notification of a volume level change on an ACXVOLUME object so that ACX can generate a corresponding event.

## -parameters

### -param Volume

An ACXVOLUME object whose volume level has changed. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects). 

## -remarks

### Example

Example usage is shown below.

```cpp
    PCODEC_VOLUME_TIMER_CONTEXT timerCtx = GetCodecVolumeTimerContext(Timer);
    PCODEC_VOLUME_ELEMENT_CONTEXT volumeCtx = GetCodecVolumeElementContext(timerCtx->VolumeElement);

    // Toggle volume between max and min
    for (ULONG i = 0; i < MAX_CHANNELS; ++i)
    {
        volumeCtx->VolumeLevel[i] = volumeCtx->VolumeLevel[i] == VOLUME_LEVEL_MAXIMUM ? VOLUME_LEVEL_MINIMUM : VOLUME_LEVEL_MAXIMUM;
    }

    AcxVolumeChangeLevelNotification(timerCtx->VolumeElement);
```

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


