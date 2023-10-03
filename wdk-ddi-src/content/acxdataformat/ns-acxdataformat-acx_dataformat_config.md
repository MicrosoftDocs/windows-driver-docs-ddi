---
UID: NS:acxdataformat._ACX_DATAFORMAT_CONFIG
tech.root: audio
title: ACX_DATAFORMAT_CONFIG
ms.date: 05/31/2022
targetos: Windows
description: The ACX_DATAFORMAT_CONFIG structure is used to configure a new ACX data format object.
prerelease: false
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
req.typenames: ACX_DATAFORMAT_CONFIG, *PACX_DATAFORMAT_CONFIG
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - acxdataformat.h
api_name:
 - _ACX_DATAFORMAT_CONFIG
 - PACX_DATAFORMAT_CONFIG
 - ACX_DATAFORMAT_CONFIG
f1_keywords:
 - _ACX_DATAFORMAT_CONFIG
 - acxdataformat/_ACX_DATAFORMAT_CONFIG
 - PACX_DATAFORMAT_CONFIG
 - acxdataformat/PACX_DATAFORMAT_CONFIG
 - ACX_DATAFORMAT_CONFIG
 - acxdataformat/ACX_DATAFORMAT_CONFIG
dev_langs:
 - c++
---

## -description

The **ACX_DATAFORMAT_CONFIG** structure is used to configure a new ACX data format object.

## -struct-fields

### -field Size

The size of all of the data in the **ACX_DATAFORMAT_CONFIG** structure in bytes. This field is set by the [ACX_DATAFORMAT_CONFIG_INIT](nf-acxdataformat-acx_dataformat_config_init.md) function.

### -field Flags

A combination of values from the [ACX_DATAFORMAT_CONFIG_FLAGS](ne-acxdataformat-acx_dataformat_config_flags.md) enum that describe the data format.

### -field Type

An [ACX_DATAFORMAT_TYPE](ne-acxdataformat-acx_dataformat_type.md) enum value that specifies the type of the data format.

### -field u

Union of pointers to supported data formats.

### -field u.KsFormat

Pointer to the [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md) for this ACX data format.

## -remarks

Instances of the **ACX_DATAFORMAT_CONFIG** structure must be initialized by calling the [ACX_DATAFORMAT_CONFIG_INIT](nf-acxdataformat-acx_dataformat_config_init.md) function.

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_DATAFORMAT_CONFIG_INIT](nf-acxdataformat-acx_dataformat_config_init.md)
- [ACX_DATAFORMAT_CONFIG_FLAGS](ne-acxdataformat-acx_dataformat_config_flags.md)
- [ACX_DATAFORMAT_CONFIG_INIT_KS](nf-acxdataformat-acx_dataformat_config_init_ks.md)
- [acxdataformat.h header](index.md)
