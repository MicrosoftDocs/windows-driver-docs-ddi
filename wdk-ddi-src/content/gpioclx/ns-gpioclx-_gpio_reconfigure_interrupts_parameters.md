---
UID: NS:gpioclx._GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
title: "_GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS"
author: windows-driver-content
description: The GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure describes the general-purpose I/O (GPIO) interrupt pin to reconfigure.
old-location: gpio\gpio_reconfigure_interrupts_parameters.htm
old-project: GPIO
ms.assetid: 98C9CFA6-76B3-4AF7-8280-BF84CC31CF70
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, GPIO.gpio_reconfigure_interrupts_parameters, PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure pointer [Parallel Ports], gpioclx/GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure [Parallel Ports], *PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, gpioclx/PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS"
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
-	GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
product: Windows
targetos: Windows
req.typenames: "*PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS"
---

# _GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure


## -description


The <b>GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</b> structure describes the general-purpose I/O (GPIO) interrupt pin to reconfigure.


## -syntax


````
typedef struct _GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS {
  BANK_ID                          BankId;
  PIN_NUMBER                       PinNumber;
  KINTERRUPT_MODE                  InterruptMode;
  KINTERRUPT_POLARITY              Polarity;
  GPIO_RECONFIGURE_INTERRUPT_FLAGS Flags;
} GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, *PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS;
````


## -struct-fields




### -field BankId

The identifier for the bank of GPIO pins that contains the interrupt pin to reconfigure. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinNumber

The bank-relative pin number. If N is the number of pins in this bank, <b>PinNumber</b> is an integer in the range 0 to N–1. GpioClx previously obtained the number of pins in each bank from the <i>CLIENT_QueryControllerBasicInformation</i> event callback function. For more information, see the description of the <b>NumberOfPinsPerBank</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field InterruptMode

Indicates whether to configure the GPIO interrupt pin to be level-sensitive or edge-triggered (latched). This member is set to one of the following values:

<ul>
<li><b>LevelSensitive</b></li>
<li><b>Latched</b></li>
</ul>
For more information, see <a href="..\miniport\ne-miniport-_kinterrupt_mode.md">KINTERRUPT_MODE</a>.


### -field Polarity

Indicates the polarity of the reconfigured GPIO interrupt pin. For a level-sensitive interrupt, this member indicates whether the interrupt is active-high or active-low. For an edge-triggered interrupt, this member indicates whether the interrupt is triggered on the rising edge, on the falling edge, or on both edges. This member is set to one of the following values:   

<ul>
<li><b>InterruptActiveHigh</b></li>
<li><b>InterruptRisingEdge</b></li>
<li><b>InterruptActiveLow</b></li>
<li><b>InterruptFallingEdge</b></li>
<li><b>InterruptActiveBoth</b></li>
</ul>
For more information, see <a href="..\miniport\ne-miniport-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>.


### -field Flags

A set of flags to control the interrupt-reconfiguration operation. No flags are currently defined for this operation.


## -remarks



The <i>ReconfigureParameters</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698243">CLIENT_ReconfigureInterrupt</a> event callback function is a pointer to a caller-allocated <b>GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</b> structure.




## -see-also

<a href="..\miniport\ne-miniport-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="..\miniport\ne-miniport-_kinterrupt_mode.md">KINTERRUPT_MODE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698243">CLIENT_ReconfigureInterrupt</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

