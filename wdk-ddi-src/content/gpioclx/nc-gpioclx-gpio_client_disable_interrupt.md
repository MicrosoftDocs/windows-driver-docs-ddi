---
UID: NC:gpioclx.GPIO_CLIENT_DISABLE_INTERRUPT
title: GPIO_CLIENT_DISABLE_INTERRUPT
author: windows-driver-content
description: The CLIENT_DisableInterrupt event callback function disables interrupts on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.
old-location: gpio\client_disableinterrupt.htm
old-project: GPIO
ms.assetid: D9EBBE6D-BB2C-4D38-963D-1BA5E67A5420
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_disableinterrupt, CLIENT_DisableInterrupt callback function [Parallel Ports], CLIENT_DisableInterrupt, GPIO_CLIENT_DISABLE_INTERRUPT, GPIO_CLIENT_DISABLE_INTERRUPT, gpioclx/CLIENT_DisableInterrupt
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
req.irql: Called at PASSIVE_LEVEL.
topictype:
-	APIRef
-	kbSyntax
apitype:
-	UserDefined
apilocation:
-	Gpioclx.h
apiname:
-	CLIENT_DisableInterrupt
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# GPIO_CLIENT_DISABLE_INTERRUPT callback


## -description


The <i>CLIENT_DisableInterrupt</i> event callback function disables interrupts on a general-purpose I/O (GPIO) pin that is configured as an interrupt input.


## -prototype


````
GPIO_CLIENT_DISABLE_INTERRUPT CLIENT_DisableInterrupt;

NTSTATUS CLIENT_DisableInterrupt(
  _In_ PVOID                              Context,
  _In_ PGPIO_DISABLE_INTERRUPT_PARAMETERS DisableParameters
)
{ ... }
````


## -parameters




### -param Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


### -param DisableParameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698249">GPIO_DISABLE_INTERRUPT_PARAMETERS</a> structure that describes the GPIO interrupt pin.


## -returns


The <i>CLIENT_DisableInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.



## -remarks


This callback function is implemented by the GPIO controller driver. GpioClx  calls this function to disable interrupts on a GPIO pin that is configured as an interrupt request input.

To register your driver's <i>CLIENT_DisableInterrupt</i> callback function, call the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_DisableInterrupt</i> function pointer.

GpioClx always calls the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439377">CLIENT_EnableInterrupt</a> and <i>CLIENT_DisableInterrupt</i> callback functions at IRQL = PASSIVE_LEVEL. However, if the GPIO registers are memory-mapped, GpioClx calls the other interrupt-related callback functions from its ISR at DIRQL. In this case, the <i>CLIENT_EnableInterrupt</i> and <i>CLIENT_DisableInterrupt</i> functions should use the GPIO interrupt lock to synchronize their interrupt-related operations to the ISR. For more information, see <a href="https://msdn.microsoft.com/D9698A50-7CC2-463C-9E46-7FE428F3193E">Interrupt Synchronization for GPIO Controller Drivers</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698249">GPIO_DISABLE_INTERRUPT_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439377">CLIENT_EnableInterrupt</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439479">GPIO_CLIENT_REGISTRATION_PACKET</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_DisableInterrupt callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

