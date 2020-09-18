---
UID: NC:gpioclx.GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS
title: GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS (gpioclx.h)
description: The CLIENT_QueryEnabledInterrupts event callback function queries the state of a set of general-purpose I/O (GPIO) pins to determine which pins are both configured as interrupt inputs and enabled for interrupts.
old-location: gpio\client_queryenabledinterrupts.htm
tech.root: GPIO
ms.assetid: 2F09006A-EFC6-4A38-AC5D-661DA48155FA
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS callback function"]
ms.keywords: CLIENT_QueryEnabledInterrupts, CLIENT_QueryEnabledInterrupts callback, CLIENT_QueryEnabledInterrupts callback function [Parallel Ports], GPIO.client_queryenabledinterrupts, GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS, gpioclx/CLIENT_QueryEnabledInterrupts
req.header: gpioclx.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Supported starting with Windows 8.1.
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
 - GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS
 - gpioclx/GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Gpioclx.h
api_name:
 - CLIENT_QueryEnabledInterrupts
---

# GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS callback function


## -description

The <i>CLIENT_QueryEnabledInterrupts</i> event callback function queries the state of a set of general-purpose I/O (GPIO) pins to determine which pins are both configured as interrupt inputs and enabled for interrupts.

## -parameters

### -param Context 

[in]
A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.

### -param QueryEnabledParameters 

[in]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_query_enabled_interrupts_parameters">GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</a> structure. Before calling this function, the caller writes a bank ID to the <b>BankId</b> member of this structure to specify which bank of GPIO pins to query. If successful, the function writes a mask value to the <b>EnabledMask</b> member of this structure to indicate which interrupts are enabled in the specified bank.

## -returns

The <i>CLIENT_QueryEnabledInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

Starting with Windows 8.1, the GPIO controller driver can, as an option, implement a <i>CLIENT_QueryEnabledInterrupts</i> callback function. If implemented, this function is called by the GPIO framework extension (GpioClx) to determine which interrupts are enabled in a bank of GPIO pins.

The <i>QueryEnabledParameters</i> parameter points to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_query_enabled_interrupts_parameters">GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</a> structure. The caller sets the value of the <b>BankId</b> member of this structure. The <i>CLIENT_QueryEnabledInterrupts</i> function writes to the <b>EnabledMask</b> member of the structure.

To register your driver's <i>CLIENT_QueryEnabledInterrupts</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_QueryEnabledInterrupts</i> function pointer.

The <i>CLIENT_QueryEnabledInterrupts</i> function is optional. If your driver does not implement this function, set the <b>CLIENT_QueryEnabledInterrupts</b> member of the <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure to <b>NULL</b>.

If the <i>CLIENT_QueryEnabledInterrupts</i> function is implemented, GpioClx uses this function to improve driver reliability and diagnostics. GpioClx calls this function to verify that the set of interrupts enabled at the GPIO controller matches what GpioClx expects. Typically, a mismatch indicates a driver bug that can potentially cause an interrupt storm. GpioClx uses this function to do more extensive state validation in checked (debug) builds, and reduces the number of calls to this function in free (retail) builds to avoid impacting performance. If implemented, this function must directly read the hardware state instead of reading a cached or software-maintained version of the state.

GpioClx calls the <i>CLIENT_QueryEnabledInterrupts</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_QueryEnabledInterrupts</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/optional-and-required-gpio-callback-functions">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_QueryEnabledInterrupts</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_QueryEnabledInterrupts</i> callback function that is named <code>MyEvtGpioQueryEnabledInterrupts</code>, use the GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS function type, as shown in this code example:


```
GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS MyEvtGpioQueryEnabledInterrupts;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
NTSTATUS
  MyEvtGpioQueryEnabledInterrupts(
    PVOID Context,
    PGPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS QueryEnabledParameters
    )
{ ... }
```

The GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_QUERY_ENABLED_INTERRUPTS function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_client_controller_basic_information">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_query_controller_basic_information">CLIENT_QueryControllerBasicInformation</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_query_enabled_interrupts_parameters">GPIO_QUERY_ENABLED_INTERRUPTS_PARAMETERS</a>

