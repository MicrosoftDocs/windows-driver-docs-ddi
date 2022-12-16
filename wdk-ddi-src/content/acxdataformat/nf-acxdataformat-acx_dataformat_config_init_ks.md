---
UID: NF:acxdataformat.ACX_DATAFORMAT_CONFIG_INIT_KS
tech.root: audio
title: ACX_DATAFORMAT_CONFIG_INIT_KS
ms.date: 04/29/2022
targetos: Windows
description: The ACX_DATAFORMAT_CONFIG_INIT_KS function initializes an ACX_DATAFORMAT_CONFIG structure using a KS data format.
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
 - ACX_DATAFORMAT_CONFIG_INIT_KS
f1_keywords:
 - ACX_DATAFORMAT_CONFIG_INIT_KS
 - acxdataformat/ACX_DATAFORMAT_CONFIG_INIT_KS
dev_langs:
 - c++
---

## -description

The **ACX_DATAFORMAT_CONFIG_INIT_KS** function initializes an [ACX_DATAFORMAT_CONFIG](ns-acxdataformat-acx_dataformat_config.md) structure using a KS data format.

## -parameters

### -param Config [out]

A pointer to the [ACX_DATAFORMAT_CONFIG](ns-acxdataformat-acx_dataformat_config.md) structure to initialize.

### -param Format [in]

A pointer to the [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md).

## -remarks

### ACX requirements

**Minimum ACX version:** 1.0

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_DATAFORMAT_CONFIG](ns-acxdataformat-acx_dataformat_config.md)
- [KSDATAFORMAT](../ks/ns-ks-ksdataformat.md)
- [ACX_DATAFORMAT_CONFIG_INIT](nf-acxdataformat-acx_dataformat_config_init.md)
- [acxdataformat.h header](index.md)
