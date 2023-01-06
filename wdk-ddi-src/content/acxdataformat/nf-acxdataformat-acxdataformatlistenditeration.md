---
UID: NF:acxdataformat.AcxDataFormatListEndIteration
tech.root: audio
title: AcxDataFormatListEndIteration
ms.date: 12/15/2022
targetos: Windows
description: The AcxDataFormatListEndIteration function ends the iteration process on an ACX data format list.
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
 - AcxDataFormatListEndIteration
f1_keywords:
 - AcxDataFormatListEndIteration
 - acxdataformat/AcxDataFormatListEndIteration
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListEndIteration** function ends the iteration process on an ACX data format list.

## -parameters

### -param AcxDataFormatList [in]

The data format list being iterated.

### -param Iterator [in, out]

Pointer to the [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md) structure being used for iteration on *AcxDataFormatList*.

## -remarks

The memory for the *Iterator* is zeroed out by this function and cannot be recovered.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md)
- [acxdataformat.h header](index.md)
