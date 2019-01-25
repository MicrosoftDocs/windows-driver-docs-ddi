---
UID: NC:gpioclx.GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION
title: GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION (gpioclx.h)
description: The CLIENT_QueryControllerBasicInformation event callback function retrieves the hardware attributes of the general-purpose I/O (GPIO) controller.
old-location: gpio\client_querycontrollerbasicinformation.htm
tech.root: GPIO
ms.assetid: 5674317C-6785-46F5-880F-71FAF2CD3C64
ms.date: 02/15/2018
ms.keywords: CLIENT_QueryControllerBasicInformation, CLIENT_QueryControllerBasicInformation callback, CLIENT_QueryControllerBasicInformation callback function [Parallel Ports], GPIO.client_querycontrollerbasicinformation, GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION, gpioclx/CLIENT_QueryControllerBasicInformation
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Gpioclx.h
api_name:
-	CLIENT_QueryControllerBasicInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION callback function


## -description


The <i>CLIENT_QueryControllerBasicInformation</i> event callback function retrieves the hardware attributes of the general-purpose I/O (GPIO) controller.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param Information [out]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. The <i>CLIENT_QueryControllerBasicInformation</i> function writes the GPIO controller hardware attributes and configuration information into this structure.


## -returns



The <i>CLIENT_QueryControllerBasicInformation</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function.

The <i>CLIENT_QueryControllerBasicInformation</i> callback function should set all members of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure, including the <b>Version</b> and <b>Size</b> members. GpioClx does not initialize the <b>Size</b> member before calling this function, but the buffer that the <i>Information</i> parameter points to is guaranteed to be large enough to contain the version of this structure that the GPIO controller driver uses.

To register your driver's <i>CLIENT_QueryControllerBasicInformation</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_QueryControllerBasicInformation</i> function pointer.


#### Examples

To define a <i>CLIENT_QueryControllerBasicInformation</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_QueryControllerBasicInformation</i> callback function that is named <code>MyEvtGpioQueryControllerBasicInformation</code>, use the GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION MyEvtGpioQueryDeviceInformation;</pre>
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
  MyEvtGpioQueryDeviceInformation(
    PVOID Context,
    PCLIENT_CONTROLLER_BASIC_INFORMATION Information
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_QUERY_CONTROLLER_BASIC_INFORMATION function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>
 

 

