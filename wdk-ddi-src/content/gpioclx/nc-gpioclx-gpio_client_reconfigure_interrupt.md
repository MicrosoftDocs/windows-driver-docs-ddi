---
UID: NC:gpioclx.GPIO_CLIENT_RECONFIGURE_INTERRUPT
title: GPIO_CLIENT_RECONFIGURE_INTERRUPT
author: windows-driver-content
description: The CLIENT_ReconfigureInterrupt event callback function reconfigures a general-purpose I/O (GPIO) pin that is used as an interrupt input.
old-location: gpio\client_reconfigureinterrupt.htm
old-project: GPIO
ms.assetid: 2F654D79-7DB6-45C4-8E6D-2EBAEF2DA7F5
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO.client_reconfigureinterrupt, CLIENT_ReconfigureInterrupt callback function [Parallel Ports], CLIENT_ReconfigureInterrupt, GPIO_CLIENT_RECONFIGURE_INTERRUPT, GPIO_CLIENT_RECONFIGURE_INTERRUPT, gpioclx/CLIENT_ReconfigureInterrupt
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
-	CLIENT_ReconfigureInterrupt
product: Windows
targetos: Windows
req.typenames: "*PGNSS_V2UPL_NI_INFO, GNSS_V2UPL_NI_INFO"
---

# GPIO_CLIENT_RECONFIGURE_INTERRUPT callback


## -description


The <i>CLIENT_ReconfigureInterrupt</i> event callback function reconfigures a general-purpose I/O (GPIO) pin that is used as an interrupt input.


## -prototype


````
GPIO_CLIENT_RECONFIGURE_INTERRUPT CLIENT_ReconfigureInterrupt;

NTSTATUS CLIENT_ReconfigureInterrupt(
  _In_ PVOID                                   Context,
  _In_ PGPIO_RECONFIGURE_INTERRUPTS_PARAMETERS ReconfigureParameters
)
{ ... }
````


## -parameters




#### - Context [in]

A pointer to the GPIO controller driver's <a href="https://msdn.microsoft.com/4BE99C71-9BA6-44E3-A54F-DE8C3440A474">device context</a>.


#### - ReconfigureParameters [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/hh698256">GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</a> structure that specifies how to reconfigure the GPIO interrupt pin.


## -returns


The <i>CLIENT_ReconfigureInterrupt</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.



## -remarks


The GPIO framework extension (GpioClx) might call the <i>CLIENT_ReconfigureInterrupt</i> function to change the interrupt mode or interrupt polarity of a GPIO pin that is used as an interrupt input.

For example, if the GPIO controller hardware does not directly support active-both interrupts, but can be configured to support active-high and active-low level-mode interrupts, GpioClx can emulate an active-both interrupt pin by calling the <i>CLIENT_ReconfigureInterrupt</i> function to alternately configure a GPIO pin for active-high and active-low level-mode interrupts. For more information about active-both interrupts, see the description of the <b>EmulateActiveBoth</b> flag in <a href="https://msdn.microsoft.com/library/windows/hardware/hh439449">CONTROLLER_ATTRIBUTE_FLAGS</a>.

GpioClx calls the <i>CLIENT_ReconfigureInterrupt</i> callback function either at PASSIVE_LEVEL or DIRQL, depending on the device information that the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a> callback function supplies to GpioClx. The <i>CLIENT_QueryControllerBasicInformation</i> function provides device information in the form of a <a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a> structure. If the <b>MemoryMappedController</b> flag bit is set in the <b>Flags</b> member of this structure, GpioClx calls the <i>CLIENT_ReconfigureInterrupt</i> function at DIRQL, which is the IRQL at which the ISR in GpioClx runs. Otherwise, this function is called at PASSIVE_LEVEL. For more information about this flag bit, see <a href="https://msdn.microsoft.com/2F126431-13AB-4E3F-9E5E-56DC7D9AF024">Optional and Required GPIO Callback Functions</a>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439399">CLIENT_QueryControllerBasicInformation</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439358">CLIENT_CONTROLLER_BASIC_INFORMATION</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh698256">GPIO_RECONFIGURE_INTERRUPTS_PARAMETERS</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439449">CONTROLLER_ATTRIBUTE_FLAGS</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20CLIENT_ReconfigureInterrupt callback function%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

