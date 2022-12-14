---
UID: NF:acxdataformat.AcxDataFormatGetEncodedChannelCount
tech.root: audio
title: AcxDataFormatGetEncodedChannelCount
ms.date: 12/14/2022
targetos: Windows
description: The AcxDataFormatGetEncodedChannelCount function gets the channel count for the specified encoded data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: <= DISPATCH_LEVEL
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
 - AcxDataFormatGetEncodedChannelCount
f1_keywords:
 - AcxDataFormatGetEncodedChannelCount
 - acxdataformat/AcxDataFormatGetEncodedChannelCount
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetEncodedChannelCount** function gets the channel count for the specified encoded data format.

## -parameters

### -param DataFormat [in]

The encoded data format for which to retrieve the channel count.

## -returns

Returns a ULONG value that contains the channel count for the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [Representing Formats for IEC 61937 Transmissions](/windows/win32/coreaudio/representing-formats-for-iec-61937-transmissions)
- [acxdataformat.h header](index.md)
