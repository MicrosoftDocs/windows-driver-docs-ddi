---
UID: NF:acxdataformat.AcxDataFormatListBeginIteration
tech.root: audio
title: AcxDataFormatListBeginIteration
ms.date: 05/31/2022
targetos: Windows
description: The AcxDataFormatListBeginIteration function gets an ACX_DATAFORMAT_LIST_ITERATOR to use for iterating through the specified data format list.
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
 - AcxDataFormatListBeginIteration
f1_keywords:
 - AcxDataFormatListBeginIteration
 - acxdataformat/AcxDataFormatListBeginIteration
dev_langs:
 - c++
---

## -description

The **AcxDataFormatListBeginIteration** function initializes an [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md) to use for iterating through the specified data format list.

## -parameters

### -param AcxDataFormatList [in]

The data format list to iterate.

### -param Iterator [in, out]

A pointer to an [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md) structure to use for iterating the specified *AcxDataFormatList*.

## -remarks

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md)
- [acxdataformat.h header](index.md)

