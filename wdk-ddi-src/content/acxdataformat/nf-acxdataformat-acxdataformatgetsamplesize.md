---
UID: NF:acxdataformat.AcxDataFormatGetSampleSize
tech.root: audio
title: AcxDataFormatGetSampleSize
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatGetSampleSize function gets the sample size for the specified data format.
prerelease: true
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.idl: 
req.include-header: 
req.irql: DISPATCH_LEVEL
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
 - AcxDataFormatGetSampleSize
f1_keywords:
 - AcxDataFormatGetSampleSize
 - acxdataformat/AcxDataFormatGetSampleSize
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetSampleSize** function gets the sample size for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the sample size.

## -returns

Returns a ULONG value containing the sample size for the specified *DataFormat*.

## -remarks

Specifies the sample size of the data, for fixed sample sizes, or zero, if the format has a variable sample size.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxdataformat.h header](index.md)
