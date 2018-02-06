---
UID: NC:gpioclx.GPIO_CLIENT_MASK_INTERRUPTS
title: GPIO_CLIENT_MASK_INTERRUPTS
author: windows-driver-content
description: The CLIENT_MaskInterrupts event callback function masks interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.
old-location: gpio\client_maskinterrupts.htm
old-project: GPIO
ms.assetid: 0E0480BA-0F9D-4AD4-8FEC-35B3757494B9
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_maskinterrupts, CLIENT_MaskInterrupts callback function [Parallel Ports], CLIENT_MaskInterrupts, GPIO_CLIENT_MASK_INTERRUPTS, GPIO_CLIENT_MASK_INTERRUPTS, gpioclx/CLIENT_MaskInterrupts
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
-	CLIENT_MaskInterrupts
product: Windows
targetos: Windows
req.typenames: GNSS_V2UPL_NI_INFO, *PGNSS_V2UPL_NI_INFO
---

# GPIO_CLIENT_MASK_INTERRUPTS callback


## -description


The <i>CLIENT_MaskInterrupts</i> event callback function masks interrupts on a set of general-purpose I/O (GPIO) pins that are configured as interrupt inputs.


## -prototype


````
GPIO_CLIENT_MASK_INTERRUPTS CLIENT_MaskInterrupts;

NTSTATUS CLIENT_MaskInterrupts(
  _In_    PVOID                           Context,
  _Inout_ PGPIO_MASK_INTERRUPT_PARAMETERS MaskParameters
)
{ ... }
````


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



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698252">GPIO_MASK_INTERRUPT_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_MaskInterrupts callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

