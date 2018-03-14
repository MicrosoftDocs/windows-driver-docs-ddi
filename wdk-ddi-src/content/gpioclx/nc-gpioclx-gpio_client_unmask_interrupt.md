---
UID: NC:gpioclx.GPIO_CLIENT_UNMASK_INTERRUPT
title: GPIO_CLIENT_UNMASK_INTERRUPT
author: windows-driver-content
description: The CLIENT_UnmaskInterrupt event callback function unmasks the interrupt on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.
old-location: gpio\client_unmaskinterrupt.htm
old-project: GPIO
ms.assetid: 7A97B3B2-2B7B-4661-8C0D-C2234F796EA8
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: CLIENT_UnmaskInterrupt, CLIENT_UnmaskInterrupt callback function [Parallel Ports], GPIO.client_unmaskinterrupt, GPIO_CLIENT_UNMASK_INTERRUPT, gpioclx/CLIENT_UnmaskInterrupt
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: See Remarks.
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	Gpioclx.h
api_name:
-	CLIENT_UnmaskInterrupt
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_UNMASK_INTERRUPT callback


## -description


The <i>CLIENT_UnmaskInterrupt</i> event callback function unmasks the interrupt on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.


## -prototype


````
GPIO_CLIENT_UNMASK_INTERRUPT CLIENT_UnmaskInterrupt;

NTSTATUS CLIENT_UnmaskInterrupt(
  _In_ PVOID                             Context,
  _In_ PGPIO_ENABLE_INTERRUPT_PARAMETERS InterruptParameters
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param InterruptParameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh406464">GPIO_ENABLE_INTERRUPT_PARAMETERS</a> structure that specifies a GPIO pin and describes the interrupt attributes of this pin.


## -returns



The <i>CLIENT_UnmaskInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to unmask interrupts on a GPIO pin that is configured as an interrupt request input. For more information, see <a href="https://msdn.microsoft.com/FD6537DA-2AAA-4646-896D-D5BC834526B6">GPIO Interrupt Masks</a>.

To register your driver's <i>CLIENT_UnmaskInterrupt</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_UnmaskInterrupt</i> function pointer.

The <i>CLIENT_UnmaskInterrupt</i> function is called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_UnmaskInterrupt</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_UnmaskInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_UnmaskInterrupt</i> callback function that is named <code>MyEvtGpioUnmaskInterrupt</code>, use the GPIO_CLIENT_UNMASK_INTERRUPT function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_UNMASK_INTERRUPT MyEvtGpioUnmaskInterrupt;</pre>
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
  MyEvtGpioUnmaskInterrupt(
    PVOID Context,
    PGPIO_ENABLE_INTERRUPT_PARAMETERS InterruptParameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_UNMASK_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_UNMASK_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406464">GPIO_ENABLE_INTERRUPT_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>



 

 


