---
UID: NE:pepfx._GPIO_PIN_CONFIG_TYPE
title: _GPIO_PIN_CONFIG_TYPE (pepfx.h)
description: The GPIO_PIN_CONFIG_TYPE enumeration describes a connection IO resource.
old-location: kernel\gpio_pin_config_type.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["GPIO_PIN_CONFIG_TYPE enumeration"]
ms.keywords: GPIO_PIN_CONFIG_TYPE, GPIO_PIN_CONFIG_TYPE enumeration [Kernel-Mode Driver Architecture], PullDefault, PullDown, PullNone, PullUp, _GPIO_PIN_CONFIG_TYPE, kernel.gpio_pin_config_type, pepfx/GPIO_PIN_CONFIG_TYPE, pepfx/PullDefault, pepfx/PullDown, pepfx/PullNone, pepfx/PullUp
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: GPIO_PIN_CONFIG_TYPE
f1_keywords:
 - _GPIO_PIN_CONFIG_TYPE
 - pepfx/_GPIO_PIN_CONFIG_TYPE
 - GPIO_PIN_CONFIG_TYPE
 - pepfx/GPIO_PIN_CONFIG_TYPE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - pepfx.h
api_name:
 - GPIO_PIN_CONFIG_TYPE
---

# _GPIO_PIN_CONFIG_TYPE enumeration (pepfx.h)


## -description

The <b>GPIO_PIN_CONFIG_TYPE</b> enumeration describes a connection IO resource.

## -enum-fields

### -field PullDefault

Indicates that no configuration is applied to this pin.

### -field PullUp

Indicates that this pin is configured to use a pull-up resistor.

### -field PullDown

Indicates that this pin is configured to use a pull-down resistor.

### -field PullNone

Indicates that this pin is not configured to use a pull-up or pull-down resistor.

