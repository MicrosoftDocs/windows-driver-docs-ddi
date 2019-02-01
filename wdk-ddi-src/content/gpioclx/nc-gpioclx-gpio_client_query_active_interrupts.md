---
UID: NC:gpioclx.GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS
title: GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS (gpioclx.h)
description: The CLIENT_QueryActiveInterrupts event callback function queries the state of a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.
old-location: gpio\client_queryactiveinterrupts.htm
tech.root: GPIO
ms.assetid: 9B47A7B2-90C3-480F-85D8-44DD7E9F0BFA
ms.date: 02/15/2018
ms.keywords: CLIENT_QueryActiveInterrupts, CLIENT_QueryActiveInterrupts callback, CLIENT_QueryActiveInterrupts callback function [Parallel Ports], GPIO.client_queryactiveinterrupts, GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS, gpioclx/CLIENT_QueryActiveInterrupts
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
-	CLIENT_QueryActiveInterrupts
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS callback function


## -description


The <i>CLIENT_QueryActiveInterrupts</i> event callback function queries the state of a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param QueryActiveParameters [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698253">GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</a> structure that, on entry, describes the GPIO interrupt pins to query, and, on exit, contains the active and enabled interrupt state of these pins.


## -returns



The <i>CLIENT_QueryActiveInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to query a set of GPIO pins that are configured as interrupt request inputs.

The <i>QueryActiveParameters</i> parameter points to a caller-allocated <b>GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</b> structure. The caller sets the values of the <b>BankId</b> and <b>EnabledMask</b> members of this structure. The <i>CLIENT_QueryActiveInterrupts</i> function writes to the <b>ActiveMask</b> member of the structure.

On entry, the bits that are set in the <b>EnabledMask</b> member should match the set of currently enabled interrupts in the bank. On return, the bits that are set in the <b>ActiveMask</b> member should correspond to interrupts that are both enabled and active. Thus, if a bit in <b>EnabledMask</b> is zero, the corresponding bit in <b>ActiveMask</b> must be zero.

To register your driver's <i>CLIENT_QueryActiveInterrupts</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure that contains a <i>CLIENT_QueryActiveInterrupts</i> function pointer.

GpioClx calls the <i>CLIENT_QueryActiveInterrupts</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_QueryActiveInterrupts</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_QueryActiveInterrupts</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_QueryActiveInterrupts</i> callback function that is named <code>MyEvtGpioQueryActiveInterrupts</code>, use the GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS MyEvtGpioQueryActiveInterrupts;</pre>
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
  MyEvtGpioQueryActiveInterrupts(
    PVOID Context,
    PGPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS QueryActiveParameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_QUERY_ACTIVE_INTERRUPTS function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="https://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698253">GPIO_QUERY_ACTIVE_INTERRUPTS_PARAMETERS</a>
 

 

