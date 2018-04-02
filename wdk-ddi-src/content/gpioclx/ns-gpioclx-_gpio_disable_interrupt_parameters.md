---
UID: NS:gpioclx._GPIO_DISABLE_INTERRUPT_PARAMETERS
title: "_GPIO_DISABLE_INTERRUPT_PARAMETERS"
author: windows-driver-content
description: The GPIO_DISABLE_INTERRUPT_PARAMETERS structure describes a general-purpose I/O (GPIO) interrupt pin to disable.
old-location: gpio\gpio_disable_interrupt_parameters.htm
old-project: GPIO
ms.assetid: 6F71C67C-ACA6-405A-9371-9DC72CC6DDCE
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_DISABLE_INTERRUPT_PARAMETERS, GPIO.gpio_disable_interrupt_parameters, GPIO_DISABLE_INTERRUPT_PARAMETERS, GPIO_DISABLE_INTERRUPT_PARAMETERS structure [Parallel Ports], PGPIO_DISABLE_INTERRUPT_PARAMETERS, PGPIO_DISABLE_INTERRUPT_PARAMETERS structure pointer [Parallel Ports], _GPIO_DISABLE_INTERRUPT_PARAMETERS, gpioclx/GPIO_DISABLE_INTERRUPT_PARAMETERS, gpioclx/PGPIO_DISABLE_INTERRUPT_PARAMETERS"
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
-	GPIO_DISABLE_INTERRUPT_PARAMETERS
product:
- Windows
targetos: Windows
req.typenames: GPIO_DISABLE_INTERRUPT_PARAMETERS, *PGPIO_DISABLE_INTERRUPT_PARAMETERS
---

# _GPIO_DISABLE_INTERRUPT_PARAMETERS structure


## -description


The <b>GPIO_DISABLE_INTERRUPT_PARAMETERS</b> structure describes a general-purpose I/O (GPIO) interrupt pin to disable.


## -struct-fields




### -field BankId

The identifier for the bank of GPIO pins that contains the GPIO interrupt pin to disable. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinNumber

The bank-relative pin number. If N is the number pins in this bank, <b>PinNumber</b> is an integer in the range 0 to N–1. GpioClx previously obtained the number of pins in each bank from the <i>CLIENT_QueryControllerBasicInformation</i> event callback function. For more information, see the description of the <b>NumberOfPinsPerBank</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field Flags

A set of flags to control the interrupt-disable operation. The <b>RetryDisableOnFailure</b> flag bit indicates that a previous <a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a> call to disable the same pin failed. For more information, see Remarks.


## -remarks



The <i>DisableParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a> event callback function is a pointer to a caller-allocated <b>GPIO_DISABLE_INTERRUPT_PARAMETERS</b> structure.

The <i>CLIENT_DisableInterrupt</i> function for a memory-mapped GPIO controller is expected to always succeed in disabling the interrupt. However, the <i>CLIENT_DisableInterrupt</i> function for a controller that is not memory-mapped must send an I/O request to the controller to disable the interrupt, and this request might fail. If the request fails to disable the interrupt, the function must return an error status code.

After a <i>CLIENT_DisableInterrupt</i> call fails, GpioClx might retry the call one or more times. During each retry, GpioClx sets the <b>RetryDisableOnFailure</b> flag to indicate that the previous call failed. The <i>CLIENT_DisableInterrupt</i> function might respond to this flag by taking additional steps to increase the likelihood that the next attempt to disable the interrupt succeeds.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439371">CLIENT_DisableInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>
 

 

