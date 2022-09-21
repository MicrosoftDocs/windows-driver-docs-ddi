---
UID: NF:acxpin.ACX_JACK_CONFIG_INIT_ID
tech.root: audio
title: ACX_JACK_CONFIG_INIT_ID
ms.date: 07/28/2022
targetos: Windows
description: The ACX_JACK_CONFIG_INIT_ID function initializes an ACX_JACK_CONFIG structure with the specified ID.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: acxpin.h
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
 - acxpin.h
api_name:
 - ACX_JACK_CONFIG_INIT_ID
f1_keywords:
 - ACX_JACK_CONFIG_INIT_ID
 - acxpin/ACX_JACK_CONFIG_INIT_ID
dev_langs:
 - c++
---

## -description

The **ACX_JACK_CONFIG_INIT_ID** function initializes an [ACX_JACK_CONFIG](ns-acxpin-acx_jack_config.md) structure with the specified ID.

## -parameters

### -param Config [out]

A pointer to the **ACX_JACK_CONFIG** structure to initialize.

### -param Id [in]

The ID to use when initializing the **ACX_JACK_CONFIG** structure.

## -remarks

At this time, driver must use AcxJackPropertiesIdDefault as ID for the Jack.

### ACX requirements

| &nbsp; | &nbsp; |
| ---- |:---- |
| **Minimum ACX version** | 1.0 |

For more information about ACX versions, see [ACX version overview](/windows-hardware/drivers/audio/acx-version-overview).

## -see-also

- [ACX_JACK_CONFIG](ns-acxpin-acx_jack_config.md)
- [acxpin.h header](index.md)

