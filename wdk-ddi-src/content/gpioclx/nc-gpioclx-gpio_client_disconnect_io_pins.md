---
UID: NC:gpioclx.GPIO_CLIENT_DISCONNECT_IO_PINS
title: GPIO_CLIENT_DISCONNECT_IO_PINS (gpioclx.h)
description: The CLIENT_DisconnectIoPins event callback function closes a logical connection to a set of general-purpose I/O (GPIO) pins that are configured for data read or write operations.
old-location: gpio\client_disconnectiopins.htm
tech.root: GPIO
ms.date: 02/15/2018
keywords: ["GPIO_CLIENT_DISCONNECT_IO_PINS callback function"]
ms.keywords: CLIENT_DisconnectIoPins, CLIENT_DisconnectIoPins callback, CLIENT_DisconnectIoPins callback function [Parallel Ports], GPIO.client_disconnectiopins, GPIO_CLIENT_DISCONNECT_IO_PINS, gpioclx/CLIENT_DisconnectIoPins
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
targetos: Windows
req.typenames: 
f1_keywords:
 - GPIO_CLIENT_DISCONNECT_IO_PINS
 - gpioclx/GPIO_CLIENT_DISCONNECT_IO_PINS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Gpioclx.h
api_name:
 - GPIO_CLIENT_DISCONNECT_IO_PINS
---

# GPIO_CLIENT_DISCONNECT_IO_PINS callback function


## -description

The <i>CLIENT_DisconnectIoPins</i> event callback function closes a logical connection to a set of general-purpose I/O (GPIO) pins that are configured for data read or write operations.

## -parameters

### -param Context 

[in]
A pointer to the GPIO controller driver's <a href="/windows-hardware/drivers/gpio/gpio-device-contexts">device context</a>.

### -param DisconnectParameters 

[in]
A pointer to a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_disconnect_io_pins_parameters">GPIO_DISCONNECT_IO_PINS_PARAMETERS</a> structure that describes the set of GPIO pins that are to be disconnected.

## -returns

The <i>CLIENT_DisconnectIoPins</i> function returns STATUS_SUCCESS if the call is successful. Otherwise, it returns an appropriate error code.

## -remarks

This callback function is implemented by the GPIO controller driver. The GPIO framework extension (GpioClx) calls this function to close a connection that was previously opened by a call to the <a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_connect_io_pins">CLIENT_ConnectIoPins</a> callback function.

To register your driver's <i>CLIENT_DisconnectIoPins</i> callback function, call the <a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a> method. This method accepts, as an input parameter, a pointer to a <a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains a <i>CLIENT_DisconnectIoPins</i> function pointer.


#### Examples

To define a <i>CLIENT_DisconnectIoPins</i> callback function, you must first provide a function declaration that identifies the type of callback function you're defining. Windows provides a set of callback function types for drivers. Declaring a function using the callback function types helps <a href="/windows-hardware/drivers/devtest/code-analysis-for-drivers">Code Analysis for Drivers</a>, <a href="/windows-hardware/drivers/devtest/static-driver-verifier">Static Driver Verifier</a> (SDV), and other verification tools find errors, and it's a requirement for writing drivers for the Windows operating system.

For example, to define a <i>CLIENT_DisconnectIoPins</i> callback function that is named <code>MyEvtGpioDisconnectIoPins</code>, use the GPIO_CLIENT_DISCONNECT_IO_PINS function type, as shown in this code example:


```
GPIO_CLIENT_DISCONNECT_IO_PINS MyEvtGpioDisconnectIoPins;
```

Then, implement your callback function as follows:


```
_Use_decl_annotations_
NTSTATUS
  MyEvtGpioDisconnectIoPins(
    PVOID Context,
    PGPIO_DISCONNECT_IO_PINS_PARAMETERS DisconnectParameters
    )
{ ... }
```

The GPIO_CLIENT_DISCONNECT_IO_PINS function type is defined in the Gpioclx.h header file. To more accurately identify errors when you run the code analysis tools, be sure to add the _Use_decl_annotations_ annotation to your function definition. The _Use_decl_annotations_ annotation ensures that the annotations that are applied to the GPIO_CLIENT_DISCONNECT_IO_PINS function type in the header file are used. For more information about the requirements for function declarations, see <a href="/windows-hardware/drivers/devtest/declaring-functions-by-using-function-role-types-for-kmdf-drivers">Declaring Functions by Using Function Role Types for KMDF Drivers</a>. For more information about _Use_decl_annotations_, see <a href="/visualstudio/code-quality/annotating-function-behavior">Annotating Function Behavior</a>.

<div class="code"></div>

## -see-also

<a href="/windows-hardware/drivers/ddi/gpioclx/nc-gpioclx-gpio_client_connect_io_pins">CLIENT_ConnectIoPins</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_registerclient">GPIO_CLX_RegisterClient</a>



<a href="/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_disconnect_io_pins_parameters">GPIO_DISCONNECT_IO_PINS_PARAMETERS</a>

