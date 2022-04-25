---
UID: NS:acxdataformat._ACX_DATAFORMAT_LIST_CONFIG
tech.root: audio
title: ACX_DATAFORMAT_LIST_CONFIG
ms.date: 03/30/2022
targetos: Windows
description: The ACX_DATAFORMAT_LIST_CONFIG structure is used to configure a new ACX data format list object.
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
req.typenames: ACX_DATAFORMAT_LIST_CONFIG, *PACX_DATAFORMAT_LIST_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdataformat.h
api_name:
 - _ACX_DATAFORMAT_LIST_CONFIG
 - PACX_DATAFORMAT_LIST_CONFIG
 - ACX_DATAFORMAT_LIST_CONFIG
f1_keywords:
 - _ACX_DATAFORMAT_LIST_CONFIG
 - acxdataformat/_ACX_DATAFORMAT_LIST_CONFIG
 - PACX_DATAFORMAT_LIST_CONFIG
 - acxdataformat/PACX_DATAFORMAT_LIST_CONFIG
 - ACX_DATAFORMAT_LIST_CONFIG
 - acxdataformat/ACX_DATAFORMAT_LIST_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_DATAFORMAT_LIST_CONFIG** structure is used to configure a new ACX data format list object.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_DATAFORMAT_LIST_CONFIG** structure in bytes. This field is set by the [ACX_DATAFORMAT_LIST_CONFIG_INIT](nf-acxdataformat-acx_dataformat_list_config_init.md) function.

### -field Flags

A combination of values from the [ACX_DATAFORMAT_LIST_CONFIG_FLAGS](ne-acxdataformat-acx_dataformat_list_config_flags.md) enum that describe the data format list.

## -remarks

Instances of the **ACX_DATAFORMAT_LIST_CONFIG** structure must be initialized by calling the [ACX_DATAFORMAT_LIST_CONFIG_INIT](nf-acxdataformat-acx_dataformat_list_config_init.md) function.

## -see-also

- [ACX_DATAFORMAT_LIST_CONFIG_INIT](nf-acxdataformat-acx_dataformat_list_config_init.md)
- [ACX_DATAFORMAT_LIST_CONFIG_FLAGS](ne-acxdataformat-acx_dataformat_list_config_flags.md)
- [acxdataformat.h header](index.md)
 
TBD - Please review this topic
