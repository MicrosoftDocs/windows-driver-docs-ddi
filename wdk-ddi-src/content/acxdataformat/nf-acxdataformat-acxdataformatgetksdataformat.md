---
UID: NF:acxdataformat.AcxDataFormatGetKsDataFormat
tech.root: audio
title: AcxDataFormatGetKsDataFormat
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatGetKsDataFormat function gets the kernel streaming data format for the specified data format.
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
 - AcxDataFormatGetKsDataFormat
f1_keywords:
 - AcxDataFormatGetKsDataFormat
 - acxdataformat/AcxDataFormatGetKsDataFormat
dev_langs:
 - c++
---

## -description

The **AcxDataFormatGetKsDataFormat** function gets the kernel streaming data format for the specified data format.

## -parameters

### -param DataFormat [in]

The data format for which to retrieve the kernel streaming format.

## -returns

Returns a pointer to the [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md) structure associated with the specified *DataFormat*.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [acxdataformat.h header](index.md)

