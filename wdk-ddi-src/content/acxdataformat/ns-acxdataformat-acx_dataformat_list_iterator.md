---
UID: NS:acxdataformat._ACX_DATAFORMAT_LIST_ITERATOR
tech.root: audio
title: ACX_DATAFORMAT_LIST_ITERATOR
ms.date: 03/30/2022
targetos: Windows
description: The ACX_DATAFORMAT_LIST_ITERATOR structure holds the state of iteration over an ACX data format list.
prerelease: true
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: acxdataformat.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: ACX_DATAFORMAT_LIST_ITERATOR, *PACX_DATAFORMAT_LIST_ITERATOR
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdataformat.h
api_name:
 - _ACX_DATAFORMAT_LIST_ITERATOR
 - PACX_DATAFORMAT_LIST_ITERATOR
 - ACX_DATAFORMAT_LIST_ITERATOR
f1_keywords:
 - _ACX_DATAFORMAT_LIST_ITERATOR
 - acxdataformat/_ACX_DATAFORMAT_LIST_ITERATOR
 - PACX_DATAFORMAT_LIST_ITERATOR
 - acxdataformat/PACX_DATAFORMAT_LIST_ITERATOR
 - ACX_DATAFORMAT_LIST_ITERATOR
 - acxdataformat/ACX_DATAFORMAT_LIST_ITERATOR
dev_langs:
 - c++
---

## -description

The **ACX_DATAFORMAT_LIST_ITERATOR** structure holds the state of iteration over an ACX data format list.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_DATAFORMAT_LIST_ITERATOR** structure in bytes. This field is set by the [ACX_DATAFORMAT_LIST_ITERATOR_INIT](nf-acxdataformat-acx_dataformat_list_iterator_init.md) function.

### -field Flags

A combination of values from the [ACX_DATAFORMAT_LIST_ITERATOR_CONFIG_FLAGS](ne-acxdataformat-acx_dataformat_list_iterator_config_flags.md) enum that describe the data format list iterator.

### -field Reserved

Reserved.

## -remarks

This structure should not be directly updated. Instances of the **ACX_DATAFORMAT_LIST_ITERATOR** structure must be initialized by calling the [ACX_DATAFORMAT_LIST_ITERATOR_INIT](nf-acxdataformat-acx_dataformat_list_iterator_init.md) function.

## -see-also

- [ACX_DATAFORMAT_LIST_ITERATOR_INIT](nf-acxdataformat-acx_dataformat_list_iterator_init.md)
- [ACX_DATAFORMAT_LIST_ITERATOR_CONFIG_FLAGS](ne-acxdataformat-acx_dataformat_list_iterator_config_flags.md)

TBD - Please review this topic
