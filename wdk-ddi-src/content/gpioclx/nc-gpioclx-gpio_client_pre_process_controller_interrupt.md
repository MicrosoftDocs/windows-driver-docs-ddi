---
UID: NC:gpioclx.GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT
title: GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT
author: windows-driver-content
description: The CLIENT_PreProcessControllerInterrupt event callback function performs any pre-processing of a general-purpose I/O (GPIO) interrupt that must be done immediately if the ISR is scheduled to run at a later time.
old-location: gpio\client_preprocesscontrollerinterrupt.htm
old-project: GPIO
ms.assetid: BC97E260-D77C-4ACD-B431-0CE6D745B37B
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: CLIENT_PreProcessControllerInterrupt, CLIENT_PreProcessControllerInterrupt callback function [Parallel Ports], GPIO.client_preprocesscontrollerinterrupt, GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT, gpioclx/CLIENT_PreProcessControllerInterrupt
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
req.irql: Called at DIRQL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_PreProcessControllerInterrupt
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT callback


## -description


The <i>CLIENT_PreProcessControllerInterrupt</i> event callback function performs any pre-processing of a general-purpose I/O (GPIO) interrupt that must be done immediately if the ISR is scheduled to run at a later time.


## -prototype


````
GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT CLIENT_PreProcessControllerInterrupt;

NTSTATUS CLIENT_PreProcessControllerInterrupt(
  _In_ PVOID   Context,
  _In_ BANK_ID BankId
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param BankId [in]

The bank that contains the interrupting GPIO pin. If N is the number of banks in the GPIO controller, <b>BankId</b> is an integer in the range 0 to N–1. The GPIO framework extension previously obtained the number of banks in the controller from the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> event callback function. For more information, see Remarks in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>.


### -param EnabledMask








## -returns



The <i>CLIENT_PreProcessControllerInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.




## -remarks



This callback function is optional. A GPIO controller driver implements this function only if it performs most of its interrupt handling at PASSIVE_LEVEL, but must do some initial processing of an interrupt at DIRQL.

Typically, a GPIO controller driver can access a memory-mapped GPIO controller at DIRQL, but can access a serially connected GPIO controller only at PASSIVE_LEVEL. However, some serially connected GPIO controllers might lose interrupt status data if they delay capture of the interrupt status bits until the IRQL drops to PASSIVE_LEVEL. When the IRQL later drops to PASSIVE_LEVEL, the GPIO framework extension (GpioClx) can call the driver's <a href="https://msdn.microsoft.com/library/windows/hardware/hh439395">CLIENT_QueryActiveInterrupts</a> callback function to retrieve the register contents.

The GPIO controller driver indicates whether it must handle interrupts at PASSIVE_LEVEL in the device information that it passes to GpioClx during the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback. If the GPIO controller is memory-mapped, so that the driver can access the controller's registers at DIRQL, the driver sets the <b>MemoryMappedController</b> flag bit in the <b>Flags</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure that the driver passes to GpioClx. Otherwise, the driver sets <b>MemoryMappedController</b> = 0 to indicate that the driver must handle interrupts at PASSIVE_LEVEL. For more information, see <a href="https://msdn.microsoft.com/E7556046-D85C-4CD1-8C27-578BF5CAFF2B">Passive-Level ISRs</a>.

To register your driver's <i>CLIENT_PreProcessControllerInterrupt</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_PreProcessControllerInterrupt</i> function pointer.


#### Examples

To define a <i>CLIENT_PreProcessControllerInterrupt</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="https://msdn.microsoft.com/2F3549EF-B50F-455A-BDC7-1F67782B8DCA">Code Analysis for Drivers</a>, <a href="https://msdn.microsoft.com/74feeb16-387c-4796-987a-aff3fb79b556">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_PreProcessControllerInterrupt</i> callback function that is named <code>MyEvtGpioPreProcessInterrupt</code>, use the GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT function type, as shown in this code example:

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT MyEvtGpioPreProcessInterrupt;</pre>
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
  MyEvtGpioPreProcessInterrupt(
    PVOID Context
    )
{ ... }</pre>
</td>
</tr>
</table></span></div>
The GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_PRE_PROCESS_CONTROLLER_INTERRUPT function type in the header file are used. For more information about the requirements for function declarations, see <a href="https://msdn.microsoft.com/73a408ba-0219-4fde-8dad-ca330e4e67c3">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="http://go.microsoft.com/fwlink/p/?LinkId=286697">Annotating Function Behavior</a>.

<div class="code"></div>



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_PreProcessControllerInterrupt callback function%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

