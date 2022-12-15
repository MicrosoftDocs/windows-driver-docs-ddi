---
UID: NF:acxdataformat.AcxDataFormatGetEncodedSamplesPerSec
tech.root: audio
title: AcxDataFormatGetEncodedSamplesPerSec
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatGetEncodedSamplesPerSec function gets the number of samples per second of audio for the specified encoded data format.
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
 - AcxDataFormatGetEncodedSamplesPerSec
f1_keywords:
 - AcxDataFormatGetEncodedSamplesPerSec
 - acxdataformat/AcxDataFormatGetEncodedSamplesPerSec
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetEncodedSamplesPerSec** function gets the number of samples per second of audio for the specified encoded data format.

## -parameters

### -param DataFormat [in]

The encoded data format for which to retrieve the samples per second.

## -returns

Returns a ULONG value that contains the number of samples per second of audio for the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [Representing Formats for IEC 61937 Transmissions](/windows/win32/coreaudio/representing-formats-for-iec-61937-transmissions)
- [acxdataformat.h header](index.md)

