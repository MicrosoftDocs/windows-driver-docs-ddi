---
UID: NC:gpioclx.GPIO_CLIENT_READ_PINS_MASK
title: GPIO_CLIENT_READ_PINS_MASK
author: windows-driver-content
description: The CLIENT_ReadGpioPinsUsingMask event callback function reads a bank of general-purpose I/O (GPIO) pins.
old-location: gpio\client_readgpiopinsusingmask.htm
old-project: GPIO
ms.assetid: EFF7C3D8-9E52-446A-BF55-0308A0D2835E
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: CLIENT_ReadGpioPinsUsingMask, CLIENT_ReadGpioPinsUsingMask callback function [Parallel Ports], GPIO.client_readgpiopinsusingmask, GPIO_CLIENT_READ_PINS_MASK, gpioclx/CLIENT_ReadGpioPinsUsingMask
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_ReadGpioPinsUsingMask
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_READ_PINS_MASK callback


## -description


The <i>CLIENT_ReadGpioPinsUsingMask</i> event callback function reads a bank of general-purpose I/O (GPIO) pins.


## -prototype


````
GPIO_CLIENT_READ_PINS_MASK CLIENT_ReadGpioPinsUsingMask;

NTSTATUS CLIENT_ReadGpioPinsUsingMask(
  _In_    PVOID                           Context,
  _Inout_ PGPIO_READ_PINS_MASK_PARAMETERS ReadParameters
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param ReadParameters [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698254">GPIO_READ_PINS_MASK_PARAMETERS</a> structure that, on entry, describes the GPIO pins to read, and, on exit, contains the data read from the GPIO pins.


## -returns



The <i>CLIENT_ReadGpioPinsUsingMask</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is implemented by the GPIO controller driver. The GpioClx calls this function.

The <i>CLIENT_ReadGpioPinsUsingMask</i> callback function reads the values of all of the GPIO pins in a bank of pins. The function stores these values in the <b>PinValues</b> member of the <b>GPIO_READ_PINS_MASK_PARAMETERS</b> structure. Bit 0 (the least significant bit) of this member contains the value of pin 0, bit 1 contains the value of pin 1, and so on.

To register your driver's <i>CLIENT_ReadGpioPinsUsingMask</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_ReadGpioPinsUsingMask</i> function pointer.

The <i>CLIENT_ReadGpioPinsUsingMask</i> function can be called from the interrupt service routine (ISR) in GpioClx. This ISR runs either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, the GpioClx ISR runs at DIRQL and calls the <i>CLIENT_ReadGpioPinsUsingMask</i> function at DIRQL. Otherwise, the ISR runs at PASSIVE_LEVEL and calls the function at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.


#### Examples

To define a <i>CLIENT_ReadGpioPinsUsingMask</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_ReadGpioPinsUsingMask</i> callback function that is named <code>MyEvtGpioReadGpioPinsUsingMask</code>, use the GPIO_CLIENT_READ_PINS_MASK function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_READ_PINS_MASK MyEvtGpioReadPinsUsingMask;</pre>
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
  MyEvtGpioReadPinsUsingMask(
    PVOID Context,
    PGPIO_READ_PINS_MASK_PARAMETERS ReadParameters
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_READ_PINS_MASK function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_READ_PINS_MASK function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh698254">GPIO_READ_PINS_MASK_PARAMETERS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ReadGpioPinsUsingMask callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

