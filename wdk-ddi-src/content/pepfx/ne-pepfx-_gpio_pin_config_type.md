---
UID: NE:pepfx._GPIO_PIN_CONFIG_TYPE
title: "_GPIO_PIN_CONFIG_TYPE"
author: windows-driver-content
description: The GPIO_PIN_CONFIG_TYPE enumeration describes a connection IO resource.
old-location: kernel\gpio_pin_config_type.htm
old-project: kernel
ms.assetid: 76509992-E5A7-4C2F-84D3-B3FD06ACEFE1
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: pepfx/GPIO_PIN_CONFIG_TYPE, PullUp, kernel.gpio_pin_config_type, GPIO_PIN_CONFIG_TYPE, pepfx/PullNone, PullDefault, pepfx/PullUp, _GPIO_PIN_CONFIG_TYPE, pepfx/PullDefault, PullNone, PullDown, pepfx/PullDown, GPIO_PIN_CONFIG_TYPE enumeration [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pepfx.h
req.include-header: 
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
req.irql: See Remarks.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	GPIO_PIN_CONFIG_TYPE
product: Windows
targetos: Windows
req.typenames: GPIO_PIN_CONFIG_TYPE
---

# _GPIO_PIN_CONFIG_TYPE enumeration


## -description


The <b>GPIO_PIN_CONFIG_TYPE</b> enumeration describes a connection IO resource.


## -syntax


````
typedef enum _GPIO_PIN_CONFIG_TYPE { 
  PullDefault,
  PullUp,
  PullDown,
  PullNone
} GPIO_PIN_CONFIG_TYPE;
````


## -enum-fields




### -field PullDefault

Indicates that no configuration is applied to this pin.


### -field PullUp

Indicates that this pin is configured to use a pull-up resistor.


### -field PullDown

Indicates that this pin is configured to use a pull-down resistor.


### -field PullNone

Indicates that this pin is not configured to use a pull-up or pull-down resistor.

