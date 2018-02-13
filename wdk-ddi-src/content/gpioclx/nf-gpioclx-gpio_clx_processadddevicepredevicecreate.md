---
UID: NF:gpioclx.GPIO_CLX_ProcessAddDevicePreDeviceCreate
title: GPIO_CLX_ProcessAddDevicePreDeviceCreate function
author: windows-driver-content
description: The GPIO_CLX_ProcessAddDevicePreDeviceCreate method loads initialization information into two structures that are passed as input parameters to the WdfDeviceCreate method.
old-location: gpio\gpio_clx_processadddevicepredevicecreate.htm
old-project: GPIO
ms.assetid: 8492CCCB-2BA9-419D-A22F-DE06D08D4CC7
ms.author: windowsdriverdev
ms.date: 12/14/2017
ms.keywords: GPIO_CLX_ProcessAddDevicePreDeviceCreate, gpioclx/GPIO_CLX_ProcessAddDevicePreDeviceCreate, GPIO_CLX_ProcessAddDevicePreDeviceCreate method [Parallel Ports], GPIO.gpio_clx_processadddevicepredevicecreate
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
-	GPIO_CLX_ProcessAddDevicePreDeviceCreate
product: Windows
targetos: Windows
req.typenames: GPIO_CONNECT_IO_PINS_MODE, *PGPIO_CONNECT_IO_PINS_MODE
---

# GPIO_CLX_ProcessAddDevicePreDeviceCreate function


## -description


The <b>GPIO_CLX_ProcessAddDevicePreDeviceCreate</b> method loads initialization information into two structures that are passed as input parameters to the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> method.


## -syntax


````
NTSTATUS GPIO_CLX_ProcessAddDevicePreDeviceCreate(
  _In_    WDFDRIVER              Driver,
  _Inout_ PWDFDEVICE_INIT        DeviceInit,
  _Out_   PWDF_OBJECT_ATTRIBUTES FdoAttributes
);
````


## -parameters




### -param Driver [in]

A WDFDRIVER handle to the framework driver object for the GPIO controller driver.


### -param DeviceInit [in, out]

A pointer to a framework-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> structure. This method loads initialization information into this structure. On return, this structure is ready to be used as an input parameter to the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> method.


### -param FdoAttributes [out]

A pointer to a caller-allocated <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure. This method loads initialization information into this structure. On return, this structure is ready to be used as an input parameter to the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> method.


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



Your GPIO controller driver must call this method in its <a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a> callback function, before the call to the <a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a> method that creates the device object (FDO) that represents the GPIO controller. Otherwise, the GPIO framework extension (GpioClx) cannot handle I/O requests or process interrupts for the new framework device object.


#### Examples

The following code example shows the <i>EvtDriverDeviceAdd</i> callback function in the GPIO controller driver for an "XYZ" GPIO controller device.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS
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
                                                      &amp;FdoAttributes);
    if (!NT_SUCCESS(Status)) {
        goto ExitDeviceAdd;
    }

    //
    // Call the framework to create the device and attach it to the lower stack.
    //

    Status = WdfDeviceCreate(&amp;DeviceInit, &amp;FdoAttributes, &amp;Device);
    if (!NT_SUCCESS(Status)) {
        goto ExitDeviceAdd;
    }

    Status = GPIO_CLX_ProcessAddDevicePostDeviceCreate(Driver, Device);
    if (!NT_SUCCESS(Status)) {
        goto ExitDeviceAdd;
    }

ExitDeviceAdd:
    return Status;
}</pre>
</td>
</tr>
</table></span></div>
In the preceding code example, the <b>WdfDeviceCreate</b> call creates the framework device object that represents the GPIO controller device. The two input parameters for this call point to <a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a> and <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structures. These structures are modified by the  <b>GPIO_CLX_ProcessAddDevicePreDeviceCreate</b> call, which precedes the <b>WdfDeviceCreate</b> call. The output parameter, <i>Device</i>, from the <b>WdfDeviceCreate</b> call is an input parameter to the <a href="https://msdn.microsoft.com/library/windows/hardware/hh439484">GPIO_CLX_ProcessAddDevicePostDeviceCreate</a> call, which follows the <b>WdfDeviceCreate</b> call.

<div class="code"></div>



## -see-also

<a href="..\wdfdriver\nc-wdfdriver-evt_wdf_driver_device_add.md">EvtDriverDeviceAdd</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff546951">WDFDEVICE_INIT</a>



<a href="..\wdfdevice\nf-wdfdevice-wdfdevicecreate.md">WdfDeviceCreate</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439484">GPIO_CLX_ProcessAddDevicePostDeviceCreate</a>



<a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [GPIO\parports]:%20GPIO_CLX_ProcessAddDevicePreDeviceCreate method%20 RELEASE:%20(12/14/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

