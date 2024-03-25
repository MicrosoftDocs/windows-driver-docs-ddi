---
UID: NF:acxdataformat.AcxDataFormatGetValidBitsPerSample
tech.root: audio
title: AcxDataFormatGetValidBitsPerSample
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatGetValidBitsPerSample function gets the valid number of bits per sample for the specified data format.
prerelease: false
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
 - AcxDataFormatGetValidBitsPerSample
f1_keywords:
 - AcxDataFormatGetValidBitsPerSample
 - acxdataformat/AcxDataFormatGetValidBitsPerSample
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetValidBitsPerSample** function gets the valid number of bits per sample for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the valid number of bits per sample.

## -returns

Returns a ULONG value containing the valid number bits per sample for the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxdataformat.h header](index.md)
