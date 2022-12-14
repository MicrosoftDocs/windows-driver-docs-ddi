---
UID: NF:acxdataformat.AcxDataFormatGetEncodedAverageBytesPerSec
tech.root: audio
title: AcxDataFormatGetEncodedAverageBytesPerSec
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatGetEncodedAverageBytesPerSec function gets the required bytes-per-second transfer rate for the specified encoded data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: <= DISPATCH_LEVEL
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
 - AcxDataFormatGetEncodedAverageBytesPerSec
f1_keywords:
 - AcxDataFormatGetEncodedAverageBytesPerSec
 - acxdataformat/AcxDataFormatGetEncodedAverageBytesPerSec
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetEncodedAverageBytesPerSec** function gets the required bytes-per-second transfer rate for the specified encoded data format.

## -parameters

### -param DataFormat [in]

The encoded data format for which to retrieve the required bytes-per-second transfer rate.

## -returns

Returns a ULONG value that contains the required bytes-per-second transfer rate for the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [Representing Formats for IEC 61937 Transmissions](/windows/win32/coreaudio/representing-formats-for-iec-61937-transmissions)
- [acxdataformat.h header](index.md)

