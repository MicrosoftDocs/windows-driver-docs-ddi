---
UID: NS:gpioclx._GPIO_READ_PINS_MASK_PARAMETERS
title: "_GPIO_READ_PINS_MASK_PARAMETERS"
author: windows-driver-content
description: The GPIO_READ_PINS_MASK_PARAMETERS structure describes a read operation on a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\gpio_read_pins_mask_parameters.htm
old-project: GPIO
ms.assetid: 679C9A71-7F39-4344-93D0-6B1332D76CF7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.gpio_read_pins_mask_parameters, *PGPIO_READ_PINS_MASK_PARAMETERS, gpioclx/GPIO_READ_PINS_MASK_PARAMETERS, GPIO_READ_PINS_MASK_PARAMETERS structure [Parallel Ports], PGPIO_READ_PINS_MASK_PARAMETERS, GPIO_READ_PINS_MASK_PARAMETERS, PGPIO_READ_PINS_MASK_PARAMETERS structure pointer [Parallel Ports], gpioclx/PGPIO_READ_PINS_MASK_PARAMETERS, _GPIO_READ_PINS_MASK_PARAMETERS
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 8.
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Gpioclx.h
apiname:
-	GPIO_READ_PINS_MASK_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PGPIO_READ_PINS_MASK_PARAMETERS, GPIO_READ_PINS_MASK_PARAMETERS"
---

# _GPIO_READ_PINS_MASK_PARAMETERS structure


## -description


The <b>GPIO_READ_PINS_MASK_PARAMETERS</b> structure describes a read operation on a bank of general-purpose I/O (GPIO) pins.


## -syntax


````
typedef struct _GPIO_READ_PINS_MASK_PARAMETERS {
  BANK_ID              BankId;
  PULONG64             PinValues;
  GPIO_READ_PINS_FLAGS Flags;
  PVOID                Reserved;
} GPIO_READ_PINS_MASK_PARAMETERS, *PGPIO_READ_PINS_MASK_PARAMETERS;
````


## -struct-fields




### -field BankId

The identifier for this bank of GPIO pins. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinValues

A 64-bit variable to which the GPIO controller driver stores the values that it reads from the GPIO pins in the bank. If N is the number of GPIO pins in this bank, the pins are numbered 0 to N–1. The value from pin number 0 is saved in bit 0 (the least significant bit) of this variable, the value from pin number 1 is saved in bit 1 of this variable, and so on.


### -field Flags

A set of flags to control the GPIO pin read operation. If the <b>WriteConfiguredPins</b> flag bit is set, the GPIO controller driver can read from a GPIO pin that is configured for write operations.


### -field Reserved

Reserved for system use.


## -remarks


The <i>ReadParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439406">CLIENT_ReadGpioPinsUsingMask</a> event callback function is a pointer to a caller-allocated <b>GPIO_READ_PINS_MASK_PARAMETERS</b> structure.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439406">CLIENT_ReadGpioPinsUsingMask</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_READ_PINS_MASK_PARAMETERS structure%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

