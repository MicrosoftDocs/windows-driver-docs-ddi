---
UID: NS:gpioclx._GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
title: _GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS (gpioclx.h)
description: The GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure describes the general-purpose I/O (GPIO) interrupt pin to reconfigure.
old-location: gpio\gpio_reconfigure_interrupts_parameters.htm
tech.root: GPIO
ms.date: 02/15/2018
keywords: ["GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure"]
ms.keywords: "*PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, GPIO.gpio_reconfigure_interrupts_parameters, GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure [Parallel Ports], PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure pointer [Parallel Ports], _GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, gpioclx/GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, gpioclx/PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS"
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
req.irql: 
targetos: Windows
req.typenames: GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS, *PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
f1_keywords:
 - _GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
 - gpioclx/_GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
 - PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
 - gpioclx/PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
 - GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
 - gpioclx/GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Gpioclx.h
api_name:
 - GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS
---

# _GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS structure


## -description

The <b>GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</b> structure describes the general-purpose I/O (GPIO) interrupt pin to reconfigure.

## -struct-fields

### -field BankId

The identifier for the bank of GPIO pins that contains the interrupt pin to reconfigure. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension (GpioClx) previously obtained the number of banks in the controller from the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

### -field PinNumber

The bank-relative pin number. If N is the number of pins in this bank, <b>PinNumber</b> is an integer in the range 0 to N–1. GpioClx previously obtained the number of pins in each bank from the <i>CLIENT_QueryControllerBasicInformation</i> event callback function. For more information, see the description of the <b>NumberOfPinsPerBank</b> member in <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.

### -field InterruptMode

Indicates whether to configure the GPIO interrupt pin to be level-sensitive or edge-triggered (latched). This member is set to one of the following values:

<ul>
<li><b>LevelSensitive</b></li>
<li><b>Latched</b></li>
</ul>
For more information, see <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>.

### -field Polarity

Indicates the polarity of the reconfigured GPIO interrupt pin. For a level-sensitive interrupt, this member indicates whether the interrupt is active-high or active-low. For an edge-triggered interrupt, this member indicates whether the interrupt is triggered on the rising edge, on the falling edge, or on both edges. This member is set to one of the following values:   

<ul>
<li><b>InterruptActiveHigh</b></li>
<li><b>InterruptRisingEdge</b></li>
<li><b>InterruptActiveLow</b></li>
<li><b>InterruptFallingEdge</b></li>
<li><b>InterruptActiveBoth</b></li>
</ul>
For more information, see <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a>.

### -field Flags

A set of flags to control the interrupt-reconfiguration operation. No flags are currently defined for this operation.

## -remarks

The <i>ReconfigureParameters</i> parameter of the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_reconfigure_interrupt">CLIENT_ReconfigureInterrupt</a> event callback function is a pointer to a caller-allocated <b>GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</b> structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_reconfigure_interrupt">CLIENT_ReconfigureInterrupt</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_mode">KINTERRUPT_MODE</a>



<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_kinterrupt_polarity">KINTERRUPT_POLARITY</a>
