---
UID: NS:gpioclx._GPIO_WRITE_PINS_PARAMETERS
title: "_GPIO_WRITE_PINS_PARAMETERS"
author: windows-driver-content
description: The GPIO_WRITE_PINS_PARAMETERS structure describes a write operation on a group of general-purpose I/O (GPIO) pins.
old-location: gpio\gpio_write_pins_parameters.htm
old-project: GPIO
ms.assetid: 5607AFBA-2C8C-4637-81E8-7940CF9E989A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_WRITE_PINS_PARAMETERS, GPIO.gpio_write_pins_parameters, GPIO_WRITE_PINS_PARAMETERS, GPIO_WRITE_PINS_PARAMETERS structure [Parallel Ports], PGPIO_WRITE_PINS_PARAMETERS, PGPIO_WRITE_PINS_PARAMETERS structure pointer [Parallel Ports], _GPIO_WRITE_PINS_PARAMETERS, gpioclx/GPIO_WRITE_PINS_PARAMETERS, gpioclx/PGPIO_WRITE_PINS_PARAMETERS"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	GPIO_WRITE_PINS_PARAMETERS
product: Windows
targetos: Windows
req.typenames: GPIO_WRITE_PINS_PARAMETERS, *PGPIO_WRITE_PINS_PARAMETERS
---

# _GPIO_WRITE_PINS_PARAMETERS structure


## -description


The <b>GPIO_WRITE_PINS_PARAMETERS</b> structure describes a write operation on a group of general-purpose I/O (GPIO) pins.


## -syntax


````
typedef struct _GPIO_WRITE_PINS_PARAMETERS {
  BANK_ID               BankId;
  PPIN_NUMBER           PinNumberTable;
  ULONG                 PinCount;
  PVOID                 Buffer;
  GPIO_WRITE_PINS_FLAGS Flags;
  PVOID                 Reserved;
} GPIO_WRITE_PINS_PARAMETERS, *PGPIO_WRITE_PINS_PARAMETERS;
````


## -struct-fields




### -field BankId

The identifier for the bank of GPIO pins that contains the pins to write to. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinNumberTable

A pointer to an array of bank-relative PIN_NUMBER values. Each array element specifies the number of a GPIO pin to write to. If this bank has N pins, the pins are numbered 0 to N–1. The number of elements in this array is specified by the <b>PinCount</b> member.


### -field PinCount

The number of elements in the <b>PinNumberTable</b> array.


### -field Buffer

A pointer to a buffer that contains the bit values that this callback function is to write to the GPIO pins that are identified in the <b>PinNumberTable</b> array. The function writes bit 0 (the least significant bit) from the buffer to the GPIO pin that is identified by array element 0, writes bit 1 from the buffer to the pin identified by array element 1, and so on.


### -field Flags

A set of flags to control the GPIO pin write operation. No flags are currently defined for this operation.


### -field Reserved

Reserved for system use.


## -remarks



The <i>WriteParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439439">CLIENT_WriteGpioPins</a> event callback function is a pointer to a caller-allocated <b>GPIO_WRITE_PINS_PARAMETERS</b> structure. All of the pins that this function writes to are part of the same bank of GPIO pins.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439439">CLIENT_WriteGpioPins</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_WRITE_PINS_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

