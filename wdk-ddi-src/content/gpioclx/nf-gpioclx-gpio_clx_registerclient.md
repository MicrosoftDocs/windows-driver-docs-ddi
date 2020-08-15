---
UID: NF:gpioclx.GPIO_CLX_RegisterClient
title: GPIO_CLX_RegisterClient function (gpioclx.h)
description: The GPIO_CLX_RegisterClient method registers a general-purpose I/O (GPIO) controller driver as a client of the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_registerclient.htm
tech.root: GPIO
ms.assetid: C87385E0-7B3F-44DA-90D0-E644C58AB375
ms.date: 02/15/2018
keywords: ["GPIO_CLX_RegisterClient function"]
ms.keywords: GPIO.gpio_clx_registerclient, GPIO_CLX_RegisterClient, GPIO_CLX_RegisterClient method [Parallel Ports], gpioclx/GPIO_CLX_RegisterClient
f1_keywords:
 - "gpioclx/GPIO_CLX_RegisterClient"
 - "GPIO_CLX_RegisterClient"
req.header: gpioclx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.lib: Msgpioclxstub.lib
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Msgpioclxstub.lib
- Msgpioclxstub.dll
api_name:
- GPIO_CLX_RegisterClient
targetos: Windows
req.typenames: 
---

# GPIO_CLX_RegisterClient function


## -description


The <b>GPIO_CLX_RegisterClient</b> method registers a general-purpose I/O (GPIO) controller driver as a client of the GPIO framework extension (GpioClx).


## -parameters




### -param Driver 
[in]
A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


### -param RegistrationPacket 
[in, out]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a> structure that contains the caller's registration information. This structure contains pointers to the event callback functions that the GPIO controller driver implements. Additionally, this structure specifies the size of the device context that the GPIO controller driver requires for its internal configuration data and state information.


### -param RegistryPath 
[in]
A pointer to a <a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a> structure that contains the path name of the registry key for the  GPIO controller driver. This parameter should be the registry path name that was passed to the driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a> routine. For more information about driver registry keys, see <a href="https://docs.microsoft.com/windows-hardware/drivers/install/overview-of-registry-trees-and-keys">Registry Trees for Devices and Drivers</a>.


## -returns



<b>GPIO_CLX_RegisterClient</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The <i>Driver</i>, <i>RegistrationPacket</i>, or <i>RegistryPath</i> parameter is NULL.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_GPIO_INVALID_REGISTRATION_PACKET</b></dt>
</dl>
</td>
<td width="60%">
The specified registration packet is not valid.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Out of memory.

</td>
</tr>
</table>
 




## -remarks



The GPIO controller driver calls this method to register its event callback functions with GpioClx. Typically, the driver calls this method from its <b>DriverEntry</b> routine, which runs shortly after the driver is loaded into memory.

Later, just before the GPIO controller driver unloads, the driver calls the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_unregisterclient">GPIO_CLX_UnregisterClient</a> method to cancel its registration with GpioClx.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/driverentry-of-ide-controller-minidriver">DriverEntry</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/ns-gpioclx-_gpio_client_registration_packet">GPIO_CLIENT_REGISTRATION_PACKET</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_unregisterclient">GPIO_CLX_UnregisterClient</a>



<a href="https://docs.microsoft.com/windows/desktop/api/ntdef/ns-ntdef-_unicode_string">UNICODE_STRING</a>
 

 

