---
UID: NS:gpioclx._GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS
title: "_GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS"
author: windows-driver-content
description: The GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS structure describes the input and output buffers for a controller-specific operation.
old-location: gpio\gpio_client_controller_specific_function_parameters.htm
old-project: GPIO
ms.assetid: 57EE1369-09A5-423F-8025-0863B449A909
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS, GPIO.gpio_client_controller_specific_function_parameters, GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS, GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS structure [Parallel Ports], PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS, PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS structure pointer [Parallel Ports], _GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS, gpioclx/GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS, gpioclx/PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: gpioclx.h
req.include-header: 
req.target-type: Windows
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Gpioclx.h
api_name:
-	GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS
product: Windows
targetos: Windows
req.typenames: GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS, *PGPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS
---

# _GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS structure


## -description


The <b>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</b> structure describes the input and output buffers for a controller-specific operation.


## -struct-fields




### -field InputBuffer

A pointer to an input buffer from which the general-purpose I/O (GPIO) controller driver reads the input parameters for the controller-specific operation. This member can be NULL if the operation does not require input parameters.


### -field InputBufferLength

The size, in bytes, of the input buffer pointed to by <b>InputBuffer</b>.


### -field OutputBuffer

A pointer to an output buffer to which the GPIO controller driver writes the results for the controller-specific operation. This member can be NULL if the operation does not require output parameters.


### -field OutputBufferLength

The size, in bytes, of the output buffer pointed to by <b>OutputBuffer</b>.


### -field BytesWritten

The number of bytes written to the output buffer. The GPIO controller driver sets the value of this member to indicate how much data was written to the output buffer. If no data was written to the output buffer, or if <b>OutputBuffer</b> = NULL, the driver should set <b>BytesWritten</b> = 0.


## -remarks



The <i>Parameters</i> parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh698237">CLIENT_ControllerSpecificFunction</a> function is a pointer to a <b>GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS</b> structure. This structure describes the input and output buffers from a custom I/O control request (IOCTL) for a hardware-specific operation that is implemented by the GPIO controller and supported by the GPIO controller driver.

The GPIO framework extension (GpioClx) fills in the first four members of the structure before the call to the <i>CLIENT_ControllerSpecificFunction</i> function. This function fills in the last member, <b>BytesWritten</b>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh698237">CLIENT_ControllerSpecificFunction</a>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLIENT_CONTROLLER_SPECIFIC_FUNCTION_PARAMETERS structure%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

