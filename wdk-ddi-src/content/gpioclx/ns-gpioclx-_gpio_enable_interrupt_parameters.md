---
UID: NS:gpioclx._GPIO_ENABLE_INTERRUPT_PARAMETERS
title: "_GPIO_ENABLE_INTERRUPT_PARAMETERS"
author: windows-driver-content
description: The GPIO_ENABLE_INTERRUPT_PARAMETERS structure specifies a general-purpose I/O (GPIO) pin and describes the interrupt attributes of this pin.
old-location: gpio\gpio_enable_interrupt_parameters.htm
old-project: GPIO
ms.assetid: 9F9AA4C1-A202-4AF8-8E1D-F7E56C08A2C1
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_GPIO_ENABLE_INTERRUPT_PARAMETERS, GPIO_ENABLE_INTERRUPT_PARAMETERS, PGPIO_ENABLE_INTERRUPT_PARAMETERS structure pointer [Parallel Ports], *PGPIO_ENABLE_INTERRUPT_PARAMETERS, GPIO.gpio_enable_interrupt_parameters, gpioclx/GPIO_ENABLE_INTERRUPT_PARAMETERS, GPIO_ENABLE_INTERRUPT_PARAMETERS structure [Parallel Ports], gpioclx/PGPIO_ENABLE_INTERRUPT_PARAMETERS, PGPIO_ENABLE_INTERRUPT_PARAMETERS"
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
-	GPIO_ENABLE_INTERRUPT_PARAMETERS
product: Windows
targetos: Windows
req.typenames: GPIO_ENABLE_INTERRUPT_PARAMETERS, *PGPIO_ENABLE_INTERRUPT_PARAMETERS
---

# _GPIO_ENABLE_INTERRUPT_PARAMETERS structure


## -description


The <b>GPIO_ENABLE_INTERRUPT_PARAMETERS</b> structure specifies a general-purpose I/O (GPIO) pin and describes the interrupt attributes of this pin.


## -syntax


````
typedef struct _GPIO_ENABLE_INTERRUPT_PARAMETERS {
  BANK_ID                     BankId;
  PIN_NUMBER                  PinNumber;
  GPIO_ENABLE_INTERRUPT_FLAGS Flags;
  KINTERRUPT_MODE             InterruptMode;
  KINTERRUPT_POLARITY         Polarity;
  UCHAR                       PullConfiguration;
  USHORT                      DebounceTimeout;
  PVOID                       VendorData;
  ULONG                       VendorDataLength;
} GPIO_ENABLE_INTERRUPT_PARAMETERS, *PGPIO_ENABLE_INTERRUPT_PARAMETERS;
````


## -struct-fields




### -field BankId

The identifier for the bank that contains the GPIO pin. If M is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to M–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field PinNumber

The bank-relative pin number. If N is the number pins in this bank, <i>PinNumber</i> is an integer in the range 0 to N–1. GpioClx previously obtained the number of pins in each bank from the <i>CLIENT_QueryControllerBasicInformation</i> event callback function. For more information, see the description of the <b>NumberOfPinsPerBank</b> member in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -field Flags

A set of flags that control the configuration of the GPIO pins. No flags are currently defined for this member.


### -field InterruptMode

Whether the interrupt request from this GPIO pin is level-sensitive or edge-triggered. This member is set to one of the following values:

<ul>
<li><b>LevelSensitive</b></li>
<li><b>Latched</b></li>
</ul>
For more information, see <a href="..\miniport\ne-miniport-_kinterrupt_mode.md">KINTERRUPT_MODE</a>.


### -field Polarity

Whether the interrupt line from this GPIO pin is active-high or active-low. This member is set to one of the following values:

<ul>
<li><b>InterruptActiveHigh</b></li>
<li><b>InterruptRisingEdge</b></li>
<li><b>InterruptActiveLow</b></li>
<li><b>InterruptFallingEdge</b></li>
<li><b>InterruptActiveBoth</b></li>
</ul>
For more information, see <a href="..\miniport\ne-miniport-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>.


### -field PullConfiguration

Whether this GPIO pin is pulled up or pulled down. This member is typically set to one of the following system-defined constants:

<ul>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLDEFAULT</b></li>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLUP</b></li>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLDOWN</b></li>
<li><b>GPIO_PIN_PULL_CONFIGURATION_PULLNONE</b></li>
</ul>
If none of these constants appropriately describes the pin configuration, this member can be set to a vendor-defined constant in the range 128-255. For more information about these constants, see <a href="https://msdn.microsoft.com/B8091F53-C9B7-4A22-BDE3-4156370ABA83">GPIO_PIN_PULL_CONFIGURATION</a>.


### -field DebounceTimeout

The debounce time in units of 10 microseconds. For example, a debounce time of 5.84 milliseconds is specified as 584. The debounce time is the time required for an input signal to stabilize at a high level after the start of a low-to-high transition, or at a low level after the start of a high-to-low transition. For example, if an interrupt signal is generated by a mechanical switch, the debounce time is the time required for the metal contact in the switch to stop bouncing after the switch is turned on or off.


### -field VendorData

A pointer to a caller-allocated buffer that contains vendor-defined data for this GPIO pin. This member is optional and is set to NULL if no vendor-defined data is available. For more information about vendor-defined data, see the description of the <i>GPIO connection descriptor</i> in revision 5.0 of the Advanced Configuration and Power Interface specification (the ACPI 5.0 specification) at the <a href="http://www.acpi.info">ACPI</a> website.


### -field VendorDataLength

The size, in bytes, of the data buffer that is pointed to by the <b>VendorData</b> member.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/hh439377">CLIENT_EnableInterrupt</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/hh439435">CLIENT_UnmaskInterrupt</a> event callback functions use a <b>GPIO_ENABLE_INTERRUPT_PARAMETERS</b> structure to specify a GPIO pin and to describe the interrupt attributes of this pin.


    The <b>GPIO_PIN_PULL_CONFIGURATION_<i>XXX</i></b> constants specify whether a general-purpose I/O (GPIO) pin is pulled up or pulled down.
   


<pre class="syntax">#define GPIO_PIN_PULL_CONFIGURATION_DEFAULT (0x0)
#define GPIO_PIN_PULL_CONFIGURATION_PULLUP (0x1)
#define GPIO_PIN_PULL_CONFIGURATION_PULLDOWN (0x2)
#define GPIO_PIN_PULL_CONFIGURATION_NONE (0x3)</pre>




The <b>PullConfiguration</b> member of the <b>GPIO_ENABLE_INTERRUPT_PARAMETERS</b> structure is set to a <b>GPIO_PIN_PULL_CONFIGURATION_<i>XXX</i></b> constant.

If none of the system-defined <b>GPIO_PIN_PULL_CONFIGURATION_<i>XXX</i></b> constants appropriately describes the pin configuration, this member can be set to a vendor-defined constant in the range 128 to 255.




## -see-also

<a href="..\miniport\ne-miniport-_kinterrupt_polarity.md">KINTERRUPT_POLARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439435">CLIENT_UnmaskInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439377">CLIENT_EnableInterrupt</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="..\miniport\ne-miniport-_kinterrupt_mode.md">KINTERRUPT_MODE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_ENABLE_INTERRUPT_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

