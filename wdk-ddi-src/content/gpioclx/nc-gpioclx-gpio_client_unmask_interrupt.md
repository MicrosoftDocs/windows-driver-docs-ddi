---
UID: NC:gpioclx.GPIO_CLIENT_UNMASK_INTERRUPT
title: GPIO_CLIENT_UNMASK_INTERRUPT (gpioclx.h)
description: The CLIENT_UnmaskInterrupt event callback function unmasks the interrupt on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.
old-location: gpio\client_unmaskinterrupt.htm
tech.root: GPIO
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_UNMASK_INTERRUPT callback function"]
ms.keywords: CLIENT_UnmaskInterrupt, CLIENT_UnmaskInterrupt callback, CLIENT_UnmaskInterrupt callback function [Parallel Ports], GPIO.client_unmaskinterrupt, GPIO_CLIENT_UNMASK_INTERRUPT, gpioclx/CLIENT_UnmaskInterrupt
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
 - GPIO_CLIENT_UNMASK_INTERRUPT
 - gpioclx/GPIO_CLIENT_UNMASK_INTERRUPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Gpioclx.h
api_name:
 - GPIO_CLIENT_UNMASK_INTERRUPT
---

# GPIO_CLIENT_UNMASK_INTERRUPT callback function


## -description

The <i>CLIENT_UnmaskInterrupt</i> event callback function unmasks the interrupt on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.

## -parameters

### -param Context 

[in]
A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.

### -param InterruptParameters 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_enable_interrupt_parameters">GPIO_ENABLE_INTERRUPT_PARAMETERS</a> structure that specifies a GPIO pin and describes the interrupt attributes of this pin.

## -returns

The <i>CLIENT_UnmaskInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to unmask interrupts on a GPIO pin that is configured as an interrupt request input. For more information, see <a href="/windows-hardware/drivers/gpio/gpio-interrupt-masks">GPIO Interrupt Masks</a>.

To register your driver's <i>CLIENT_UnmaskInterrupt</i> callback function, call the <a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_UnmaskInterrupt</i> function pointer.

The <i>CLIENT_UnmaskInterrupt</i> function is called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_UnmaskInterrupt</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_UnmaskInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_UnmaskInterrupt</i> callback function that is named <code>MyEvtGpioUnmaskInterrupt</code>, use the GPIO_CLIENT_UNMASK_INTERRUPT function type, as shown in this code example:


```
GPIO_CLIENT_UNMASK_INTERRUPT MyEvtGpioUnmaskInterrupt;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
NTSTATUS
  MyEvtGpioUnmaskInterrupt(
    PVOID Context,
    PGPIO_ENABLE_INTERRUPT_PARAMETERS InterruptParameters
    )
{ ... }
```

The GPIO_CLIENT_UNMASK_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_UNMASK_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_enable_interrupt_parameters">GPIO_ENABLE_INTERRUPT_PARAMETERS</a>

