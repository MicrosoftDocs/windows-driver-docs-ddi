---
UID: NF:acxdataformat.AcxDataFormatIsEqual
tech.root: audio
title: AcxDataFormatIsEqual
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatIsEqual function compares two ACXDATAFORMAT objects for equality.
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
 - AcxDataFormatIsEqual
f1_keywords:
 - AcxDataFormatIsEqual
 - acxdataformat/AcxDataFormatIsEqual
dev_langs:
 - c++
---

## -description

The **AcxDataFormatIsEqual** function compares two [ACXDATAFORMAT](index.md) objects for equality.

## -parameters

### -param DataFormat1 [in]

The first [ACXDATAFORMAT](index.md) object to compare.

### -param DataFormat2 [in]

The second [ACXDATAFORMAT](index.md) object to compare.

## -returns

Returns TRUE if *DataFormat1* and DataFormat2 are equal, otherwise FALSE.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [acxdataformat.h header](index.md)
