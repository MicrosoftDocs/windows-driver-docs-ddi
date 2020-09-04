---
UID: NF:gpioclx.GPIO_CLX_ProcessAddDevicePreDeviceCreate
title: GPIO_CLX_ProcessAddDevicePreDeviceCreate function (gpioclx.h)
description: The GPIO_CLX_ProcessAddDevicePreDeviceCreate method loads initialization information into two structures that are passed as input parameters to the WdfDeviceCreate method.
old-location: gpio\gpio_clx_processadddevicepredevicecreate.htm
tech.root: GPIO
ms.assetid: 8492CCCB-2BA9-419D-A22F-DE06D08D4CC7
ms.date: 02/15/2018
keywords: ["GPIO_CLX_ProcessAddDevicePreDeviceCreate function"]
ms.keywords: GPIO.gpio_clx_processadddevicepredevicecreate, GPIO_CLX_ProcessAddDevicePreDeviceCreate, GPIO_CLX_ProcessAddDevicePreDeviceCreate method [Parallel Ports], gpioclx/GPIO_CLX_ProcessAddDevicePreDeviceCreate
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
targetos: Windows
req.typenames: 
f1_keywords:
 - GPIO_CLX_ProcessAddDevicePreDeviceCreate
 - gpioclx/GPIO_CLX_ProcessAddDevicePreDeviceCreate
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - LibDef
api_location:
 - Msgpioclxstub.lib
 - Msgpioclxstub.dll
api_name:
 - GPIO_CLX_ProcessAddDevicePreDeviceCreate
---

# GPIO_CLX_ProcessAddDevicePreDeviceCreate function


## -description

The <b>GPIO_CLX_ProcessAddDevicePreDeviceCreate</b> method loads initialization information into two structures that are passed as input parameters to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> method.

## -parameters

### -param Driver 

[in]
A WDFDRIVER handle to the framework driver object for the GPIO controller driver.

### -param DeviceInit 

[in, out]
A pointer to a framework-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. This method loads initialization information into this structure. On return, this structure is ready to be used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> method.

### -param FdoAttributes 

[out]
A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure. This method loads initialization information into this structure. On return, this structure is ready to be used as an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> method.

## -returns

<b>GPIO_CLX_ProcessAddDevicePreDeviceCreate</b> returns STATUS_SUCCESS if the call is successful. Possible return values include the following error codes.

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
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Out of memory.

</td>
</tr>
</table>

## -remarks

Your GPIO controller driver must call this method in its <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function, before the call to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> method that creates the device object (FDO) that represents the GPIO controller. Otherwise, the GPIO framework extension (GpioClx) cannot handle I/O requests or process interrupts for the new framework device object.


#### Examples

The following code example shows the <i>EvtDriverDeviceAdd</i> callback function in the GPIO controller driver for an "XYZ" GPIO controller device.


```cpp
NTSTATUS
  XyzEvtDriverDeviceAdd(
    _In_ WDFDRIVER Driver,
    _Inout_ PWDFDEVICE_INIT DeviceInit
    )
{
    WDFDEVICE Device;
    WDF_OBJECT_ATTRIBUTES FdoAttributes;
    NTSTATUS Status;

    Status = GPIO_CLX_ProcessAddDevicePreDeviceCreate(Driver,
                                                      DeviceInit,
                                                      &FdoAttributes);
    if (!NT_SUCCESS(Status)) {
        goto ExitDeviceAdd;
    }

    //
    // Call the framework to create the device and attach it to the lower stack.
    //

    Status = WdfDeviceCreate(&DeviceInit, &FdoAttributes, &Device);
    if (!NT_SUCCESS(Status)) {
        goto ExitDeviceAdd;
    }

    Status = GPIO_CLX_ProcessAddDevicePostDeviceCreate(Driver, Device);
    if (!NT_SUCCESS(Status)) {
        goto ExitDeviceAdd;
    }

ExitDeviceAdd:
    return Status;
}
```

In the preceding code example, the <b>WdfDeviceCreate</b> call creates the framework device object that represents the GPIO controller device. The two input parameters for this call point to <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structures. These structures are modified by the  <b>GPIO_CLX_ProcessAddDevicePreDeviceCreate</b> call, which precedes the <b>WdfDeviceCreate</b> call. The output parameter, <i>Device</i>, from the <b>WdfDeviceCreate</b> call is an input parameter to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_processadddevicepostdevicecreate">GPIO_CLX_ProcessAddDevicePostDeviceCreate</a> call, which follows the <b>WdfDeviceCreate</b> call.

<div class="code"></div>

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/gpioclx/nf-gpioclx-gpio_clx_processadddevicepostdevicecreate">GPIO_CLX_ProcessAddDevicePostDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>

