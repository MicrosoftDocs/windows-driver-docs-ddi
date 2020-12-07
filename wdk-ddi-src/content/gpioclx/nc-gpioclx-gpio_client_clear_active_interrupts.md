---
UID: NC:gpioclx.GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS
title: GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS (gpioclx.h)
description: The CLIENT_ClearActiveInterrupts event callback function clears active interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.
old-location: gpio\client_clearactiveinterrupts.htm
tech.root: GPIO
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS callback function"]
ms.keywords: CLIENT_ClearActiveInterrupts, CLIENT_ClearActiveInterrupts callback, CLIENT_ClearActiveInterrupts callback function [Parallel Ports], GPIO.client_clearactiveinterrupts, GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS, gpioclx/CLIENT_ClearActiveInterrupts
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
 - GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS
 - gpioclx/GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Gpioclx.h
api_name:
 - CLIENT_ClearActiveInterrupts
---

# GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS callback function


## -description

The <i>CLIENT_ClearActiveInterrupts</i> event callback function clears active interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.

## -parameters

### -param Context 

[in]
A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.

### -param ClearParameters 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_clear_active_interrupts_parameters">GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</a> structure that, on entry, describes the GPIO interrupt pins to clear, and, on exit, contains the status of the clear operation.

## -returns

The <i>CLIENT_ClearActiveInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

This callback function is implemented by the general-purpose I/O (GPIO) controller driver. The GPIO framework extension (GpioClx) calls this function to clear active interrupts on GPIO pins that are configured as interrupt request inputs.

This callback function is optional. If the GPIO controller hardware automatically clears active interrupt status bits when they are read, the driver should not register a <i>CLIENT_ClearActiveInterrupts</i> callback function. For more information, see <a href="/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.

To register your driver's <i>CLIENT_ClearActiveInterrupts</i> callback function, call the <a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure that contains a <i>CLIENT_ClearActiveInterrupts</i> function pointer.

GpioClx calls the <i>CLIENT_ClearActiveInterrupts</i> callback function at either PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_ClearActiveInterrupts</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="/windows-hardware/drivers/gpio/interrupt-related-callbacks">Interrupt-Related Callbacks</a>.


#### Examples

To define a <i>CLIENT_ClearActiveInterrupts</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_ClearActiveInterrupts</i> callback function that is named <code>MyEvtGpioClearActiveInterrupts</code>, use the GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS function type, as shown in this code example:


```
GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS MyEvtGpioClearActiveInterrupts;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
NTSTATUS
  MyEvtGpioClearActiveInterrupts(
    PVOID Context,
    PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS ClearParameters
    )
{ ... }
```

The GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_clear_active_interrupts_parameters">GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>
