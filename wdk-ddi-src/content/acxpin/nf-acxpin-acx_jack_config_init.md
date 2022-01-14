---
UID: NF:acxpin.ACX_JACK_CONFIG_INIT
tech.root: audio
title: ACX_JACK_CONFIG_INIT macro
ms.date: 01/13/2022
targetos: Windows
description: The ACX_JACK_CONFIG_INIT macro calls the ACX_JACK_CONFIG_INIT_ID function with the default ID value.
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
 - HeaderDef
api_location:
 - acxpin.h
api_name:
 - ACX_JACK_CONFIG_INIT
f1_keywords:
 - ACX_JACK_CONFIG_INIT
 - acxpin/ACX_JACK_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_JACK_CONFIG_INIT** macro calls the [ACX_JACK_CONFIG_INIT_ID](nf-acxpin-acx_jack_config_init_id.md) function with the default ID value.

## -syntax

```cpp
#define ACX_JACK_CONFIG_INIT(cfg) \
    ACX_JACK_CONFIG_INIT_ID(cfg, AcxJackPropertiesIdDefault)
```

## -parameters

### -param cfg

A pointer to the [ACX_JACK_CONFIG](ns-acxpin-acx_jack_config.md) structure to initialize.

## -remarks

## -see-also

- [ACX_JACK_CONFIG_INIT_ID](nf-acxpin-acx_jack_config_init_id.md)
- [ACX_JACK_CONFIG](ns-acxpin-acx_jack_config.md)
