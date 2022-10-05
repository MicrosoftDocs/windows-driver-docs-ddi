---
UID: NF:acxelements.AcxAudioEngineGetDeviceFormatList
tech.root: audio 
title: AcxAudioEngineGetDeviceFormatList
ms.date: 04/29/2022
targetos: Windows
description: The AcxAudioEngineGetDeviceFormatList function retrieves a ACXDATAFORMATLIST device format list ACX object. 
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
 - AcxAudioEngineGetDeviceFormatList
f1_keywords:
 - AcxAudioEngineGetDeviceFormatList
 - acxelements/AcxAudioEngineGetDeviceFormatList
dev_langs:
 - c++
---

## -description

The **AcxAudioEngineGetDeviceFormatList** function retrieves the ACXDATAFORMATLIST object that holds the list of supported formats for the audio engine node. For more information about ACX objects, see [Summary of ACX Objects](/windows-hardware/drivers/audio/acx-summary-of-objects).

## -parameters

### -param AudioEngine

An ACXAUDIOENGINE object that is used in a render circuit, to represent a DSP. 

## -returns

The ACXDATAFORMATLIST object which holds the list of supported formats for the specified ACXAUDIOENGINE object. 

## -remarks

### Example

Example usage is shown below.

```cpp
    status = AcxDataFormatCreate(Device, &attributes, &formatCfg, &formatPcm44100c2);
    formatCtx = GetCodecFormatContext(formatPcm44100c2);

    // Get the current audio engine device format list
    formatList = AcxAudioEngineGetDeviceFormatList(audioEngineElement);
    if (formatList == NULL)
    {
        status = STATUS_INSUFFICIENT_RESOURCES;
        goto exit;
    }

    // Add our supported formats to the audio engine device format list
    status = AcxDataFormatListAddDataFormat(formatList, formatPcm44100c2);
```

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxelements.h header](index.md)


