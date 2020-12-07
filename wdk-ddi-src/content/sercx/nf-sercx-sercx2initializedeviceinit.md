---
UID: NF:sercx.SerCx2InitializeDeviceInit
title: SerCx2InitializeDeviceInit function (sercx.h)
description: The SerCx2InitializeDeviceInit method enables version 2 of the serial framework extension (SerCx2) to register extension-specific properties with the driver framework during the creation of the framework device object for the serial controller.
old-location: serports\sercx2initializedeviceinit.htm
tech.root: serports
ms.date: 04/23/2018
keywords: ["SerCx2InitializeDeviceInit function"]
ms.keywords: 2/SerCx2InitializeDeviceInit, SerCx2InitializeDeviceInit, SerCx2InitializeDeviceInit method [Serial Ports], serports.sercx2initializedeviceinit
req.header: sercx.h
req.include-header: 
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.1.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - SerCx2InitializeDeviceInit
 - sercx/SerCx2InitializeDeviceInit
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - COM
api_location:
 - 2.0\Sercx.h
api_name:
 - SerCx2InitializeDeviceInit
---

# SerCx2InitializeDeviceInit function


## -description

The <b>SerCx2InitializeDeviceInit</b> method enables version 2 of the serial framework extension (SerCx2) to register extension-specific properties with the driver framework during the creation of the framework device object for the serial controller.

## -parameters

### -param DeviceInit 

[in, out]
A pointer to a <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure, which is an opaque structure that stores information that the Kernel Mode Driver Framework (KMDF) uses to create a framework device object. The serial controller driver receives a pointer to this structure as an input parameter to the driver's <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function.

## -returns

<b>SerCx2InitializeDeviceInit</b> returns STATUS_SUCCESS if the call is successful. Possible error return values include the following status codes.

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_REQUEST</b></dt>
</dl>
</td>
<td width="60%">
The method was called at the wrong IRQL, or the <i>DeviceInit</i> parameter is <b>NULL</b>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient resources are available to perform the requested operation.

</td>
</tr>
</table>

## -remarks

The serial controller driver must call this method from its <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> callback function before it creates a WDFDEVICE object for the serial controller.

<b>SerCx2InitializeDeviceInit</b> attaches extension-specific information to the driver's <a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a> structure. This information enables SerCx2 to perform certain actions on behalf of the serial controller driver. For example, SerCx2 receives I/O requests that clients send to the serial controller.

The serial controller driver must call <b>SerCx2InitializeDeviceInit</b> before creating a framework device object to represent the serial controller, and before calling the <a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a> method to finish initializing the device object. The driver calls a method such as <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a> to create the device object.

<b>SerCx2InitializeDeviceInit</b> sets a default security descriptor that allows both kernel-mode drivers and user-mode drivers to send I/O requests to SerCx2. The descriptor allows applications to send these requests only if they run with administrator privileges. To specify this descriptor, SerCx2 uses the following SDDL string:

<code>"D:P(A;;GA;;;SY)(A;;GA;;;BA)(A;;GA;;;UD)"</code>
If necessary, the serial controller driver can override the default setting by calling the <a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a> method with the desired security descriptor. The driver must call <b>WdfDeviceInitAssignSDDLString</b> after calling <b>SerCx2InitializeDeviceInit</b> but before calling <b>WdfDeviceCreate</b>. For more information about SDDL strings, see <a href="/windows-hardware/drivers/kernel/sddl-for-device-objects">SDDL for Device Objects</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a>



<a href="/windows-hardware/drivers/ddi/sercx/nf-sercx-sercx2initializedevice">SerCx2InitializeDevice</a>



<a href="/windows-hardware/drivers/wdf/wdfdevice_init">WDFDEVICE_INIT</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdevicecreate">WdfDeviceCreate</a>



<a href="/windows-hardware/drivers/ddi/wdfdevice/nf-wdfdevice-wdfdeviceinitassignsddlstring">WdfDeviceInitAssignSDDLString</a>
