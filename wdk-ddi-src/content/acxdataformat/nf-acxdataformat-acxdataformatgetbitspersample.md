---
UID: NF:acxdataformat.AcxDataFormatGetBitsPerSample
tech.root: audio
title: AcxDataFormatGetBitsPerSample
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatGetBitsPerSample function gets the bits per audio sample for the specified data format.
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
 - AcxDataFormatGetBitsPerSample
f1_keywords:
 - AcxDataFormatGetBitsPerSample
 - acxdataformat/AcxDataFormatGetBitsPerSample
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetBitsPerSample** function gets the bits per audio sample for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the bits per audio sample.

## -returns

Returns a ULONG value containing the number of bits per audio sample for the specified *DataFormat*.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [WAVEFORMAT structure](/windows/win32/api/mmreg/ns-mmreg-waveformat)
- [acxdataformat.h header](index.md)

