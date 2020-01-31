---
UID: NC:gpioclx.GPIO_CLIENT_DISABLE_INTERRUPT
title: GPIO_CLIENT_DISABLE_INTERRUPT (gpioclx.h)
description: The CLIENT_DisableInterrupt event callback function disables interrupts on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.
old-location: gpio\client_disableinterrupt.htm
tech.root: GPIO
ms.assetid: D9EBBE6D-BB2C-4D38-963D-1BA5E67A5420
ms.date: 02/15/2018
ms.keywords: CLIENT_DisableInterrupt, CLIENT_DisableInterrupt callback, CLIENT_DisableInterrupt callback function [Parallel Ports], GPIO.client_disableinterrupt, GPIO_CLIENT_DISABLE_INTERRUPT, gpioclx/CLIENT_DisableInterrupt
f1_keywords:
 - "gpioclx/CLIENT_DisableInterrupt"
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
req.irql: Called at PASSIVE_LEVEL.
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Gpioclx.h
api_name:
- CLIENT_DisableInterrupt
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_DISABLE_INTERRUPT callback function


## -description


The <i>CLIENT_DisableInterrupt</i> event callback function disables interrupts on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.


### -param DisableParameters [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_disable_interrupt_parameters">GPIO_DISABLE_INTERRUPT_PARAMETERS</a> structure that describes the GPIO interrupt pin.


## -returns



The <i>CLIENT_DisableInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. GpioClx  calls this function to disable interrupts on a GPIO pin that is configured as an interrupt request input.

To register your driver's <i>CLIENT_DisableInterrupt</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_DisableInterrupt</i> function pointer.

GpioClx always calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_enable_interrupt">CLIENT_EnableInterrupt</a> and <i>CLIENT_DisableInterrupt</i> callback functions at IRQL = PASSIVE_LEVEL. However, if the GPIO registers are memory-mapped, GpioClx calls the other interrupt-related callback functions from its ISR at DIRQL. In this case, the <i>CLIENT_EnableInterrupt</i> and <i>CLIENT_DisableInterrupt</i> functions should use the GPIO interrupt lock to synchronize their interrupt-related operations to the ISR. For more information, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/interrupt-synchronization-for-gpio-controller-drivers">Interrupt Synchronization for GPIO Controller Drivers</a>.


#### Examples

To define a <i>CLIENT_DisableInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_DisableInterrupt</i> callback function that is named <code>MyEvtGpioDisableInterrupt</code>, use the GPIO_CLIENT_DISABLE_INTERRUPT function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_DISABLE_INTERRUPT MyEvtGpioDisableInterrupt;</pre>
</td>
</tr>
</table></span></div>
Then, implement your callback function as follows:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>_Use_decl_annotations_
VOID
  MyEvtGpioDisableInterrupt(
    PVOID Context,
    PGPIO_DISABLE_INTERRUPT_PARAMETERS DisableParameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_DISABLE_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_DISABLE_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_enable_interrupt">CLIENT_EnableInterrupt</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_disable_interrupt_parameters">GPIO_DISABLE_INTERRUPT_PARAMETERS</a>
 

 

