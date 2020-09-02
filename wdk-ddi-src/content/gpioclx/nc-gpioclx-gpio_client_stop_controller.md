---
UID: NC:gpioclx.GPIO_CLIENT_STOP_CONTROLLER
title: GPIO_CLIENT_STOP_CONTROLLER (gpioclx.h)
description: The CLIENT_StopController event callback function performs operations that are needed to prepare the general-purpose I/O (GPIO) controller device to exit the D0 power state.
old-location: gpio\client_stopcontroller.htm
tech.root: GPIO
ms.assetid: 4B1A33AC-E341-478E-8C1E-94F4473A191C
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_STOP_CONTROLLER callback function"]
ms.keywords: CLIENT_StopController, CLIENT_StopController callback, CLIENT_StopController callback function [Parallel Ports], GPIO.client_stopcontroller, GPIO_CLIENT_STOP_CONTROLLER, gpioclx/CLIENT_StopController
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
targetos: Windows
req.typenames: 
f1_keywords:
 - GPIO_CLIENT_STOP_CONTROLLER
 - gpioclx/GPIO_CLIENT_STOP_CONTROLLER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Gpioclx.h
api_name:
 - CLIENT_StopController
---

# GPIO_CLIENT_STOP_CONTROLLER callback function


## -description

The <i>CLIENT_StopController</i> event callback function performs operations that are needed to prepare the general-purpose I/O (GPIO) controller device to exit the D0 power state.

## -parameters

### -param Context 

[in]
A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.

### -param SaveContext 

[in]
Whether the client driver should save the current hardware context of the GPIO controller device. If TRUE, the hardware context should be saved. If FALSE, the hardware context should not be saved. For more information, see Remarks.

### -param TargetState 

[in]
The target device power state. This parameter is a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/ne-wdfdevice-_wdf_power_device_state">WDF_POWER_DEVICE_STATE</a> enumeration value that specifies the low-power state that the device is to enter when it exits the D0 power state. The GPIO controller driver can use this information to determine how to configure the controller device before it leaves D0.

## -returns

The <i>CLIENT_StopController</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to prepare the GPIO controller device to be turned off or to transition to a low-power state. This callback function must perform any operations that are necessary before the device enters a low-power state, such as saving any information that the driver will need later after the device is restored to the D0 power state.

Typically, the <i>CLIENT_StopController</i> callback function configures the GPIO pins to a platform-specific initial state. For example, this function might configure all of the GPIO pins as inputs to prevent output transients from occurring when the GPIO controller device is turned off.

To register your driver's <i>CLIENT_StopController</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_StopController</i> function pointer.

Although the <i>CLIENT_StopController</i> callback function is called at IRQL = PASSIVE_LEVEL, you should not make this function pageable. The <i>CLIENT_StopController</i> callback is in the critical timing path for restoring power to the devices in the hardware platform and, for performance reasons, it should not be delayed by page faults.


#### Examples

To define a <i>CLIENT_StopController</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_StopController</i> callback function that is named <code>MyEvtGpioStopController</code>, use the GPIO_CLIENT_STOP_CONTROLLER function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_STOP_CONTROLLER  MyEvtGpioStopController;
</pre>
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
  MyEvtGpioStopController(
    PVOID Context,
    BOOLEAN RestoreContext,
    WDF_POWER_DEVICE_STATE TargetState
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_STOP_CONTROLLER function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_STOP_CONTROLLER function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>

