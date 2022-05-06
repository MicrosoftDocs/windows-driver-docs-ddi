---
UID: NF:acxdataformat.AcxDataFormatGetChannelMask
tech.root: audio
title: AcxDataFormatGetChannelMask
ms.date: 05/06/2022
targetos: Windows
description: The AcxDataFormatGetChannelMask function gets the channel mask for the specified data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
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
 - acxdataformat.h
api_name:
 - AcxDataFormatGetChannelMask
f1_keywords:
 - AcxDataFormatGetChannelMask
 - acxdataformat/AcxDataFormatGetChannelMask
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetChannelMask** function gets the [channel mask](/windows-hardware/drivers/audio/channel-mask) for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the channel mask.

## -returns

Returns a ULONGLONG value containing the channel mask.

## -remarks

The channel mask specifies the mapping of channels to speakers.

The following table shows the meaning of each bit in the channel mask:

| Bit number | Speaker position | Description           |
|------------|------------------|-----------------------|
| 0          | FL               | Front left            |
| 1          | FR               | Front right           |
| 2          | FC               | Front center          |
| 3          | LFE              | Low-frequency effects |
| 4          | BL               | Back left             |
| 5          | BR               | Back right            |
| 6          | FLC              | Front left of center  |
| 7          | FRC              | Front right of center |
| 8          | BC               | Back center           |
| 9          | SL               | Side left             |
| 10         | SR               | Side right            |

## -see-also

- [Channel Mask](/windows-hardware/drivers/audio/channel-mask)
- [acxdataformat.h header](index.md)

TBD - Please review this topic
