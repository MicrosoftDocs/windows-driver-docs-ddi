---
UID: NC:gpioclx.GPIO_CLIENT_RECONFIGURE_INTERRUPT
title: GPIO_CLIENT_RECONFIGURE_INTERRUPT (gpioclx.h)
description: The CLIENT_ReconfigureInterrupt event callback function reconfigures a general-purpose I/O (GPIO) pin that is used as an interrupt input.
old-location: gpio\client_reconfigureinterrupt.htm
tech.root: GPIO
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_RECONFIGURE_INTERRUPT callback function"]
ms.keywords: CLIENT_ReconfigureInterrupt, CLIENT_ReconfigureInterrupt callback, CLIENT_ReconfigureInterrupt callback function [Parallel Ports], GPIO.client_reconfigureinterrupt, GPIO_CLIENT_RECONFIGURE_INTERRUPT, gpioclx/CLIENT_ReconfigureInterrupt
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
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
req.irql: See Remarks.
targetos: Windows
req.typenames: 
f1_keywords:
 - GPIO_CLIENT_RECONFIGURE_INTERRUPT
 - gpioclx/GPIO_CLIENT_RECONFIGURE_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Gpioclx.h
api_name:
 - CLIENT_ReconfigureInterrupt
---

# GPIO_CLIENT_RECONFIGURE_INTERRUPT callback function


## -description

The <i>CLIENT_ReconfigureInterrupt</i> event callback function reconfigures a general-purpose I/O (GPIO) pin that is used as an interrupt input.

## -parameters

### -param Context 

[in]
A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.

### -param ReconfigureParameters 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_reconfigure_interrupts_parameters">GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</a> structure that specifies how to reconfigure the GPIO interrupt pin.

## -returns

The <i>CLIENT_ReconfigureInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

The GPIO framework extension (GpioClx) might call the <i>CLIENT_ReconfigureInterrupt</i> function to change the interrupt mode or interrupt polarity of a GPIO pin that is used as an interrupt input.

For example, if the GPIO controller hardware does not directly support active-both interrupts, but can be configured to support active-high and active-low level-mode interrupts, GpioClx can emulate an active-both interrupt pin by calling the <i>CLIENT_ReconfigureInterrupt</i> function to alternately configure a GPIO pin for active-high and active-low level-mode interrupts. For more information about active-both interrupts, see the description of the <b>EmulateActiveBoth</b> flag in <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_controller_attribute_flags">CONTROLLER_ATTRIBUTE_FLAGS</a>.

GpioClx calls the <i>CLIENT_ReconfigureInterrupt</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_ReconfigureInterrupt</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_ReconfigureInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_ReconfigureInterrupt</i> callback function that is named <code>MyEvtGpioReconfigureInterrupt</code>, use the GPIO_CLIENT_RECONFIGURE_INTERRUPT function type, as shown in this code example:


```
GPIO_CLIENT_RECONFIGURE_INTERRUPT MyEvtGpioReconfigureInterrupt;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
NTSTATUS
  MyEvtGpioReconfigureInterrupt(
    PVOID Context,
    PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS ReconfigureParameters
    )
{ ... }
```

The GPIO_CLIENT_RECONFIGURE_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_RECONFIGURE_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_controller_attribute_flags">CONTROLLER_ATTRIBUTE_FLAGS</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_reconfigure_interrupts_parameters">GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</a>
