---
UID: NF:gpioclx.GPIO_CLX_ProcessAddDevicePostDeviceCreate
title: GPIO_CLX_ProcessAddDevicePostDeviceCreate function
author: windows-driver-content
description: The GPIO_CLX_ProcessAddDevicePostDeviceCreate method passes a framework device object to the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_processadddevicepostdevicecreate.htm
old-project: GPIO
ms.assetid: 4B88820F-32B9-4AA2-867A-316A3796BE86
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: gpioclx/GPIO_CLX_ProcessAddDevicePostDeviceCreate, GPIO_CLX_ProcessAddDevicePostDeviceCreate, GPIO_CLX_ProcessAddDevicePostDeviceCreate method [Parallel Ports], GPIO.gpio_clx_processadddevicepostdevicecreate
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
-	GPIO_CLX_ProcessAddDevicePostDeviceCreate
product: Windows
targetos: Windows
req.typenames: "*PGPIO_CONNECT_IO_PINS_MODE, GPIO_CONNECT_IO_PINS_MODE"
---

# GPIO_CLX_ProcessAddDevicePostDeviceCreate function


## -description


The <b>GPIO_CLX_ProcessAddDevicePostDeviceCreate</b> method passes a framework device object to the GPIO framework extension (GpioClx).


## -syntax


````
NTSTATUS GPIO_CLX_ProcessAddDevicePostDeviceCreate(
  _In_ WDFDRIVER Driver,
  _In_ WDFDEVICE Device
);
````


## -parameters




### -param Driver [in]

A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the GPIO controller. The caller obtained this handle from the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> call that created the device object.


## -returns


<b>GPIO_CLX_ProcessAddDevicePostDeviceCreate</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.
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
The caller is not a registered client of GpioClx.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>
</td>
<td width="60%">
The framework failed to find the device name of the GPIO controller.

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


Your GPIO controller driver must call this method in its <a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a> callback function, after the call to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a> method that creates the device object (FDO) that represents the GPIO controller. Otherwise, GpioClx cannot handle I/O requests or process interrupts for the new device object.

For a code example that contains a call to <b>GPIO_CLX_ProcessAddDevicePostDeviceCreate</b>, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh439487">GPIO_CLX_ProcessAddDevicePreDeviceCreate</a>.



## -see-also

<a href="https://msdn.microsoft.com/b20db029-ee2c-4fb1-bd69-ccd2e37fdc9a">EvtDriverDeviceAdd</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545926">WdfDeviceCreate</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh439487">GPIO_CLX_ProcessAddDevicePreDeviceCreate</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_ProcessAddDevicePostDeviceCreate method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

