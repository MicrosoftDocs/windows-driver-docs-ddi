---
UID: NE:pep_x._GPIO_PIN_IORESTRICTION_TYPE
title: "_GPIO_PIN_IORESTRICTION_TYPE"
author: windows-driver-content
description: The GPIO_PIN_IORESTRICTION_TYPE enumeration describes the functions that a GPIO pin is limited to performing.
old-location: kernel\gpio_pin_iorestriction_type.htm
old-project: kernel
ms.assetid: 381A59EE-BA1C-4810-842B-1D3E4D964486
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: GPIO_PIN_IORESTRICTION_TYPE, GPIO_PIN_IORESTRICTION_TYPE enumeration [Kernel-Mode Driver Architecture], IoRestrictionInputOnly, IoRestrictionNone, IoRestrictionNoneAndPreserve, IoRestrictionOutputOnly, _GPIO_PIN_IORESTRICTION_TYPE, kernel.gpio_pin_iorestriction_type, pepfx/GPIO_PIN_IORESTRICTION_TYPE, pepfx/IoRestrictionInputOnly, pepfx/IoRestrictionNone, pepfx/IoRestrictionNoneAndPreserve, pepfx/IoRestrictionOutputOnly
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: pep_x.h
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	GPIO_PIN_IORESTRICTION_TYPE
product: Windows
targetos: Windows
req.typenames: GPIO_PIN_IORESTRICTION_TYPE, GPIO_PIN_IORESTRICTION_TYPE
---

# _GPIO_PIN_IORESTRICTION_TYPE enumeration


## -description


The <b>GPIO_PIN_IORESTRICTION_TYPE</b> enumeration describes the functions that a GPIO pin is limited to performing.


## -enum-fields




### -field IoRestrictionNone

Indicates that the GPIO pin is not restricted to either input or output. When no IO restriction is described, it is assumed to be <b>IoRestrictionNone</b>. 


### -field IoRestrictionInputOnly

Indicates that the GPIO pin is restricted to input. 


### -field IoRestrictionOutputOnly

Indicates that the GPIO pin is restricted to output. 


### -field IoRestrictionNoneAndPreserve

Indicates that the GPIO pin is not restricted to either input or output and that the mode should be preserved when the driver is unloaded. 

