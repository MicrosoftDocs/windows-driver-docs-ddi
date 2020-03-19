---
UID: NC:gpioclx.GPIO_CLIENT_RELEASE_CONTROLLER
title: GPIO_CLIENT_RELEASE_CONTROLLER (gpioclx.h)
description: The CLIENT_ReleaseController event callback function performs operations that are needed when the general-purpose I/O (GPIO) controller device is no longer accessible.
old-location: gpio\client_releasecontroller.htm
tech.root: GPIO
ms.assetid: DC73A00D-F7FA-492A-ABAF-04A5CFD85881
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_RELEASE_CONTROLLER callback function"]
ms.keywords: CLIENT_ReleaseController, CLIENT_ReleaseController callback, CLIENT_ReleaseController callback function [Parallel Ports], GPIO.client_releasecontroller, GPIO_CLIENT_RELEASE_CONTROLLER, gpioclx/CLIENT_ReleaseController
f1_keywords:
 - "gpioclx/CLIENT_ReleaseController"
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
- CLIENT_ReleaseController
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_RELEASE_CONTROLLER callback function


## -description


The <i>CLIENT_ReleaseController</i> event callback function performs operations that are needed when the general-purpose I/O (GPIO) controller device is no longer accessible.


## -parameters




### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the GPIO controller.


### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.


## -returns



The <i>CLIENT_ReleaseController</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function after the GPIO controller device is no longer accessible.

During the <i>CLIENT_ReleaseController</i> callback, the GPIO controller driver should release any hardware resources that it acquired as a result of the preceding call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_prepare_controller">CLIENT_PrepareController</a> callback function. In the case of a memory-mapped GPIO controller device, the driver should unmap the memory address range or ranges that are assigned to the hardware registers. For a controller that is not memory-mapped, the driver should close the previously opened logical connection to the controller.

To register your driver's <i>CLIENT_ReleaseController</i> callback function, call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_ReleaseController</i> function pointer.

Although the <i>CLIENT_ReleaseController</i> callback function is called at IRQL = PASSIVE_LEVEL, you should not make this function pageable. The <i>CLIENT_ReleaseController</i> callback is in the critical timing path for restoring power to the devices in the hardware platform and, for performance reasons, it should not be delayed by page faults.


#### Examples

To define a <i>CLIENT_ReleaseController</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_ReleaseController</i> callback function that is named <code>MyEvtGpioReleaseController</code>, use the GPIO_CLIENT_RELEASE_CONTROLLER function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_RELEASE_CONTROLLER  MyEvtGpioReleaseController;</pre>
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
  MyEvtGpioReleaseController(
    WDFDEVICE Device,
    PVOID Context
)
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_RELEASE_CONTROLLER function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_RELEASE_CONTROLLER function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://docs.microsoft.com/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>
 

 

