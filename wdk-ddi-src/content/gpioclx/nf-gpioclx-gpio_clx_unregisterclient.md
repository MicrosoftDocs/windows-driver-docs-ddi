---
UID: NF:gpioclx.GPIO_CLX_UnregisterClient
title: GPIO_CLX_UnregisterClient function
author: windows-driver-content
description: The GPIO_CLX_UnregisterClient method removes a general-purpose I/O (GPIO) controller driver's registration with the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_unregisterclient.htm
old-project: GPIO
ms.assetid: 2ECBF3D9-F613-4829-B2E0-FF5E21A596EC
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: GPIO_CLX_UnregisterClient, GPIO.gpio_clx_unregisterclient, gpioclx/GPIO_CLX_UnregisterClient, GPIO_CLX_UnregisterClient method [Parallel Ports]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Msgpioclxstub.lib
-	Msgpioclxstub.dll
apiname:
-	GPIO_CLX_UnregisterClient
product: Windows
targetos: Windows
req.typenames: GPIO_CONNECT_IO_PINS_MODE, *PGPIO_CONNECT_IO_PINS_MODE
---

# GPIO_CLX_UnregisterClient function


## -description


The <b>GPIO_CLX_UnregisterClient</b> method removes a general-purpose I/O (GPIO) controller driver's registration with the GPIO framework extension (GpioClx).


## -syntax


````
NTSTATUS GPIO_CLX_UnregisterClient(
  _In_ WDFDRIVER Driver
);
````


## -parameters




### -param Driver [in]

A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


## -returns



<b>GPIO_CLX_UnregisterClient</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_FOUND</b></dt>
</dl>
</td>
<td width="60%">
The caller is not a registered client of GpioClx.

</td>
</tr>
</table>
 




## -remarks



A GPIO controller driver calls this method to cancel its registration. The driver registered in a previous call to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a> method.

Typically, the GPIO controller driver calls this method from its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a> event callback function, which runs shortly before the driver unloads.




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439490">GPIO_CLX_RegisterClient</a>



<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_unload.md">EvtDriverUnload</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_UnregisterClient method%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

