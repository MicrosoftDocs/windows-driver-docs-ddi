---
UID: NF:acxpin.ACX_PIN_CONFIG_INIT
tech.root: audio
title: ACX_PIN_CONFIG_INIT macro
ms.date: 02/17/2022
targetos: Windows
description: The ACX_PIN_CONFIG_INIT macro calls the ACX_PIN_CONFIG_INIT_ID function with the default ID value.
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
 - ACX_PIN_CONFIG_INIT
f1_keywords:
 - ACX_PIN_CONFIG_INIT
 - acxpin/ACX_PIN_CONFIG_INIT
dev_langs:
 - c++
---

## -description

The **ACX_PIN_CONFIG_INIT** macro calls the [ACX_PIN_CONFIG_INIT_ID](nf-acxpin-acx_pin_config_init_id.md) function with the default ID value.

## -syntax

```cpp
#define ACX_PIN_CONFIG_INIT(cfg) \
    ACX_PIN_CONFIG_INIT_ID(cfg, AcxPinIdDefault)
```

## -parameters

### -param cfg

A pointer to the [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md) structure to initialize.

## -remarks

This call uses AcxPinIdDefault as ID for all the new added ACXPINs.

When AcxPinIdDefault is specified, ACX assignes the next sequencial ID based on the previous added ACXPINs.

## -see-also

- [ACX_PIN_CONFIG_INIT_ID](nf-acxpin-acx_pin_config_init_id.md)
- [ACX_PIN_CONFIG](ns-acxpin-acx_pin_config.md)

READY2GO
