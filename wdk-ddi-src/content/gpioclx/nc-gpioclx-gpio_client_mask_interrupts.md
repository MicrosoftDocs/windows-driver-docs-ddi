---
UID: NC:gpioclx.GPIO_CLIENT_MASK_INTERRUPTS
title: GPIO_CLIENT_MASK_INTERRUPTS (gpioclx.h)
description: The CLIENT_MaskInterrupts event callback function masks interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.
old-location: gpio\client_maskinterrupts.htm
tech.root: GPIO
ms.assetid: 0E0480BA-0F9D-4AD4-8FEC-35B3757494B9
ms.date: 02/15/2018
ms.keywords: CLIENT_MaskInterrupts, CLIENT_MaskInterrupts callback, CLIENT_MaskInterrupts callback function [Parallel Ports], GPIO.client_maskinterrupts, GPIO_CLIENT_MASK_INTERRUPTS, gpioclx/CLIENT_MaskInterrupts
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- Gpioclx.h
api_name:
- CLIENT_MaskInterrupts
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_MASK_INTERRUPTS callback function


## -description


The <i>CLIENT_MaskInterrupts</i> event callback function masks interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param MaskParameters [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698252">GPIO_MASK_INTERRUPT_PARAMETERS</a> structure that, on entry, describes the GPIO interrupt pins to mask, and, on exit, contains the status of the mask operation.


## -returns



The <i>CLIENT_MaskInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to mask interrupts on GPIO pins that are configured as interrupt request inputs. For more information, see <a href="https://msdn.microsoft.com/FD6537DA-2AAA-4646-896D-D5BC834526B6">GPIO Interrupt Masks</a>.

To register your driver's <i>CLIENT_MaskInterrupts</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure that contains a <i>CLIENT_MaskInterrupts</i> function pointer.

The <i>CLIENT_MaskInterrupts</i> function is called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_MaskInterrupts</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

A <i>CLIENT_MaskInterrupts</i> call that fails to set the interrupt mask to the requested value must set the <b>FailedMask</b> member of the <b>GPIO_MASK_INTERRUPT_PARAMETERS</b> structure to a nonzero value and return an appropriate error status code. The <i>CLIENT_MaskInterrupts</i> function for a memory-mapped GPIO controller is expected to always succeed in setting the interrupt mask to the requested value. However, the <i>CLIENT_MaskInterrupts</i> function for a controller that is not memory-mapped must send an I/O request to the  controller to set the mask, and this request might fail. If the request fails to set the mask, the function must indicate this failure in the value that it writes to the <b>FailedMask</b> member.


#### Examples

To define a <i>CLIENT_MaskInterrupts</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_MaskInterrupts</i> callback function that is named <code>MyEvtGpioMaskInterrupts</code>, use the GPIO_CLIENT_MASK_INTERRUPTS function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_MASK_INTERRUPTS MyEvtGpioMaskInterrupts;</pre>
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
  MyEvtGpioMaskInterrupts(
    PVOID Context,
    PGPIO_MASK_INTERRUPT_PARAMETERS MaskParameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_MASK_INTERRUPTS function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_MASK_INTERRUPTS function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698252">GPIO_MASK_INTERRUPT_PARAMETERS</a>
 

 

