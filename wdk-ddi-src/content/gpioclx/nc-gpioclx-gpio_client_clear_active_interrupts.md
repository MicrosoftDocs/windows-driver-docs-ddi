---
UID: NC:gpioclx.GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS
title: GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS
author: windows-driver-content
description: The CLIENT_ClearActiveInterrupts event callback function clears active interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.
old-location: gpio\client_clearactiveinterrupts.htm
old-project: GPIO
ms.assetid: 8D66F806-92BA-4A70-99F6-1C221E8752A3
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_clearactiveinterrupts, CLIENT_ClearActiveInterrupts callback function [Parallel Ports], CLIENT_ClearActiveInterrupts, GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS, GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS, gpioclx/CLIENT_ClearActiveInterrupts
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
-	CLIENT_ClearActiveInterrupts
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS callback


## -description


The <i>CLIENT_ClearActiveInterrupts</i> event callback function clears active interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.


## -prototype


````
GPIO_CLIENT_CLEAR_ACTIVE_INTERRUPTS CLIENT_ClearActiveInterrupts;

NTSTATUS CLIENT_ClearActiveInterrupts(
  _In_    PVOID                                    Context,
  _Inout_ PGPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS ClearParameters
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param ClearParameters [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698247">GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</a> structure that, on entry, describes the GPIO interrupt pins to clear, and, on exit, contains the status of the clear operation.


## -returns


The <i>CLIENT_ClearActiveInterrupts</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.



## -remarks


This callback function is implemented by the general-purpose I/O (GPIO) controller driver. The GPIO framework extension (GpioClx) calls this function to clear active interrupts on GPIO pins that are configured as interrupt request inputs.

This callback function is optional. If the GPIO controller hardware automatically clears active interrupt status bits when they are read, the driver should not register a <i>CLIENT_ClearActiveInterrupts</i> callback function. For more information, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.

To register your driver's <i>CLIENT_ClearActiveInterrupts</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <b>GPIO_CLIENT_REGISTRATION_PACKET</b> structure that contains a <i>CLIENT_ClearActiveInterrupts</i> function pointer.

GpioClx calls the <i>CLIENT_ClearActiveInterrupts</i> callback function at either PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_ClearActiveInterrupts</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/638B52A0-CB8D-4A79-B7D1-ED2474E46DAE">Interrupt-Related Callbacks</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698247">GPIO_CLEAR_ACTIVE_INTERRUPTS_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ClearActiveInterrupts callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

