---
UID: NF:acxdataformat.ACX_DATAFORMAT_LIST_ITERATOR_INIT
tech.root: audio
title: ACX_DATAFORMAT_LIST_ITERATOR_INIT
ms.date: 05/31/2022
targetos: Windows
description: The ACX_DATAFORMAT_LIST_ITERATOR_INIT function initializes an ACX_DATAFORMAT_LIST_ITERATOR structure for use by an audio class extension (ACX) driver.
prerelease: false
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
 - ACX_DATAFORMAT_LIST_ITERATOR_INIT
f1_keywords:
 - ACX_DATAFORMAT_LIST_ITERATOR_INIT
 - acxdataformat/ACX_DATAFORMAT_LIST_ITERATOR_INIT
dev_langs:
 - c++
---

## -description

The **ACX_DATAFORMAT_LIST_ITERATOR_INIT** function initializes an [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md) structure for use by an audio class extension (ACX) driver.

## -parameters

### -param Iterator [out]

A pointer to the [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md) structure to initialize.

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_DATAFORMAT_LIST_ITERATOR](ns-acxdataformat-acx_dataformat_list_iterator.md)
- [acxdataformat.h header](index.md)
