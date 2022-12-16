---
UID: NF:acxdataformat.AcxDataFormatGetSampleRate
tech.root: audio
title: AcxDataFormatGetSampleRate
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatGetSampleRate function gets the sample rate for the specified data format.
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
 - AcxDataFormatGetSampleRate
f1_keywords:
 - AcxDataFormatGetSampleRate
 - acxdataformat/AcxDataFormatGetSampleRate
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetSampleRate** function gets the sample rate for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the sample rate.

## -returns

Returns a ULONG value containing the sample rate for the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxdataformat.h header](index.md)
