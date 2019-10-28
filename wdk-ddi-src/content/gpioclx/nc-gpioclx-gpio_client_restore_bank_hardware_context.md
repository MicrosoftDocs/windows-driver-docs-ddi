---
UID: NC:gpioclx.GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT
title: GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT (gpioclx.h)
description: The CLIENT_RestoreBankHardwareContext event callback function restores the hardware context of a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_restorebankhardwarecontext.htm
tech.root: GPIO
ms.assetid: 7F73BC89-1BAF-413D-A901-56B4A0F3235A
ms.date: 02/15/2018
ms.keywords: CLIENT_RestoreBankHardwareContext, CLIENT_RestoreBankHardwareContext callback, CLIENT_RestoreBankHardwareContext callback function [Parallel Ports], GPIO.client_restorebankhardwarecontext, GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT, gpioclx/CLIENT_RestoreBankHardwareContext
ms.topic: callback
f1_keywords:
 - "gpioclx/CLIENT_RestoreBankHardwareContext"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Gpioclx.h
api_name:
- CLIENT_RestoreBankHardwareContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT callback function


## -description


The <i>CLIENT_RestoreBankHardwareContext</i> event callback function restores the hardware context of a bank of general-purpose I/O (GPIO) pins.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.


### -param Parameters [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_save_restore_bank_hardware_context_parameters">GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</a> structure that describes the bank of GPIO pins to restore.


## -returns



The <i>CLIENT_RestoreBankHardwareContext</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error status code.




## -remarks



If a bank of GPIO pins supports component-level power management, GpioClx can switch the bank to a low-power Fx state if the bank is idle. If the GPIO controller bank loses its hardware context in the Fx state, the GPIO controller driver must save this context before the F0-to-Fx transition, and, later, restore the context after the Fx-to-F0 transition. Currently, F1 is the only low-power state that is defined for GPIO controllers that use GpioClx.

GpioClx calls the <i>CLIENT_RestoreBankHardwareContext</i> function to restore the bank's previously saved hardware context. The hardware context was previously saved by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_save_bank_hardware_context">CLIENT_SaveBankHardwareContext</a> event callback function.

Some GPIO controller devices enable selected banks of pins to be turned on and off independently of other banks in the same device. Thus, power can be saved by turning off a bank that is idle.

To register your driver's <i>CLIENT_RestoreBankHardwareContext</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_RestoreBankHardwareContext</i> function pointer.

GpioClx calls the <i>CLIENT_RestoreBankHardwareContext</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_RestoreBankHardwareContext</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_RestoreBankHardwareContext</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_RestoreBankHardwareContext</i> callback function that is named <code>MyEvtGpioRestoreBankHardwareContext</code>, use the GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT MyEvtGpioRestoreBankHardwareContext;</pre>
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
NTSTATUS
  MyEvtGpioRestoreBankHardwareContext(
    PVOID Context,
    PGPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS Parameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_RESTORE_BANK_HARDWARE_CONTEXT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_save_bank_hardware_context">CLIENT_SaveBankHardwareContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_save_restore_bank_hardware_context_parameters">GPIO_SAVE_RESTORE_BANK_HARDWARE_CONTEXT_PARAMETERS</a>
 

 

