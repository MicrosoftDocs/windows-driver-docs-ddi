---
UID: NF:sercx.SerCxDeviceInitConfig
title: SerCxDeviceInitConfig function (sercx.h)
description: The SerCxDeviceInitConfig method is called by the serial controller driver to attach the serial framework extension (SerCx) to the I/O pipeline for a framework device object (FDO or PDO) that it is creating.
old-location: serports\sercxdeviceinitconfig.htm
tech.root: serports
ms.assetid: 13466A7E-D39B-4E60-AD02-2E6EFE27495A
ms.date: 04/23/2018
keywords: ["SerCxDeviceInitConfig function"]
ms.keywords: 1/SerCxDeviceInitConfig, SerCxDeviceInitConfig, SerCxDeviceInitConfig method [Serial Ports], serports.sercxdeviceinitconfig
f1_keywords:
 - "sercx/SerCxDeviceInitConfig"
 - "SerCxDeviceInitConfig"
req.header: sercx.h
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
req.lib: 
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- COM
api_location:
- 1.0\Sercx.h
api_name:
- SerCxDeviceInitConfig
targetos: Windows
req.typenames: 
---

# SerCxDeviceInitConfig function


## -description


The <b>SerCxDeviceInitConfig</b> method is called by the serial controller driver to attach the serial framework extension (SerCx) to the I/O pipeline for a framework device object (FDO or PDO) that it is creating.


## -parameters




### -param DeviceInit 
[in, out]
A pointer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure that is to be configured.


## -returns



<b>SerCxDeviceInitConfig</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status code.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Could not allocate system resources (typically memory).

</td>
</tr>
</table>
 




## -remarks



This method associates SerCx's configuration information with the <b>WDFDEVICE_INIT</b> structure for the framework device object (PDO or FDO) that is to be created. Call <b>SerCxDeviceInitConfig</b> before you call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> method to create the device object.

The controller driver's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function receives a pointer to an initialized <b>WDFDEVICE_INIT</b> structure as an input parameter.

SerCx sets a default security descriptor that the serial controller driver can, if necessary, override. For example, this default security descriptor enables a user-mode driver to send an I/O request to a peripheral device that is connected to a port on the serial controller. To change this setting in the security descriptor, the serial controller driver can call the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a> method. This call must occur after the <b>SerCxDeviceInitConfig</b> call, but before the call to the <b>WdfDeviceCreate</b> method.


#### Examples

In the following code example, a controller driver's <i>EvtDriverDeviceAdd</i> callback function passes an initialized <b>WDFDEVICE_INIT</b> structure to the <b>SerCxDeviceInitConfig</b> method. The call to <b>SerCxDeviceInitConfig</b> must occur before the <b>WdfDeviceCreate</b> call that creates the FDO for the serial controller device (UART).

<div class="code"><span codelanguage="cpp"><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>//
// FxDeviceInit is a pointer to an initialized WDFDEVICE_INIT structure.
// Drivers receive a pointer to this structure as an input parameter to an
// EvtDriverDeviceAdd callback function, or as a return value from the
// WdfControlDeviceInitAllocate method.
//

status = SerCxDeviceInitConfig(FxDeviceInit);

if (!NT_SUCCESS(status))
{
    return status;
}

// 
// Set WDF and SerCx device-level configuration options.
//

...

//
// Call the WdfDeviceCreate method.
//

...
</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a>
 

 

