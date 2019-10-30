---
UID: NF:gpioclx.GPIO_CLX_ProcessAddDevicePostDeviceCreate
title: GPIO_CLX_ProcessAddDevicePostDeviceCreate function (gpioclx.h)
description: The GPIO_CLX_ProcessAddDevicePostDeviceCreate method passes a framework device object to the GPIO framework extension (GpioClx).
old-location: gpio\gpio_clx_processadddevicepostdevicecreate.htm
tech.root: GPIO
ms.assetid: 4B88820F-32B9-4AA2-867A-316A3796BE86
ms.date: 02/15/2018
ms.keywords: GPIO.gpio_clx_processadddevicepostdevicecreate, GPIO_CLX_ProcessAddDevicePostDeviceCreate, GPIO_CLX_ProcessAddDevicePostDeviceCreate method [Parallel Ports], gpioclx/GPIO_CLX_ProcessAddDevicePostDeviceCreate
ms.topic: function
f1_keywords:
 - "gpioclx/GPIO_CLX_ProcessAddDevicePostDeviceCreate"
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
- GPIO_CLX_ProcessAddDevicePostDeviceCreate
product:
- Windows
targetos: Windows
req.typenames: 
---

# GPIO_CLX_ProcessAddDevicePostDeviceCreate function


## -description


The <b>GPIO_CLX_ProcessAddDevicePostDeviceCreate</b> method passes a framework device object to the GPIO framework extension (GpioClx).


## -parameters




### -param Driver [in]

A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


### -param Device [in]

A WDFDEVICE handle to the framework device object that represents the GPIO controller. The caller obtained this handle from the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> call that created the device object.


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



Your GPIO controller driver must call this method in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function, after the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> method that creates the device object (FDO) that represents the GPIO controller. Otherwise, GpioClx cannot handle I/O requests or process interrupts for the new device object.

For a code example that contains a call to <b>GPIO_CLX_ProcessAddDevicePostDeviceCreate</b>, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_processadddevicepredevicecreate">GPIO_CLX_ProcessAddDevicePreDeviceCreate</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_processadddevicepredevicecreate">GPIO_CLX_ProcessAddDevicePreDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>
 

 

