---
UID: NC:udecxwdfdevice.EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY
title: EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY (udecxwdfdevice.h)
description: The UDE client driver's implementation to determine the capabilities that are supported by the emulated USB host controller.
old-location: buses\evt_udecx_wdf_device_query_usb_capability.htm
tech.root: usbref
ms.date: 05/07/2018
keywords: ["EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY callback function"]
ms.keywords: EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY, EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY callback, EvtUdecxWdfDeviceQueryUsbCapability, EvtUdecxWdfDeviceQueryUsbCapability callback function [Buses], buses.evt_udecx_wdf_device_query_usb_capability, udecxwdfdevice/EvtUdecxWdfDeviceQueryUsbCapability
req.header: udecxwdfdevice.h
req.include-header: Udecx.h
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
req.kmdf-ver: 1.15
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
 - EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY
 - udecxwdfdevice/EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - UdecxWdfDevice.h
api_name:
 - EvtUdecxWdfDeviceQueryUsbCapability
---

# EVT_UDECX_WDF_DEVICE_QUERY_USB_CAPABILITY callback function


## -description

The UDE client driver's implementation to determine the capabilities that are supported by the emulated USB host controller.

## -parameters

### -param UdecxWdfDevice 

[in]
A handle to a framework device object that represents the controller. The client driver initialized this object in the previous call to <a href="/windows-hardware/drivers/ddi/udecxwdfdevice/nf-udecxwdfdevice-udecxwdfdeviceaddusbdeviceemulation">UdecxWdfDeviceAddUsbDeviceEmulation</a>.

### -param CapabilityType 

[in]
Pointer to a GUID specifying the requested capability. The possible  <i>PGUID</i>  values are  as follows:

<ul>
<li>GUID_USB_CAPABILITY_CHAINED_MDLS</li>
<li>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</li>
<li>GUID_USB_CAPABILITY_FUNCTION_SUSPEND

</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</li>
</ul>
   For information about the capabilities, see the Remarks section of <a href="/previous-versions/windows/hardware/drivers/hh406230(v=vs.85)">USBD_QueryUsbCapability</a>.

### -param OutputBufferLength 

[in]
The length, in bytes, of the request's output buffer, if an output buffer is available.

### -param OutputBuffer 

[out, optional]
A pointer to a location that receives the buffer's address. Certain capabilities may need to provide additional information
        to the USB device emulation  class extension (UdeCx)  in this buffer.

### -param ResultLength 

[out]
A location that, on return, contains the size, in bytes, of the information that the callback function stored in <i>OutputBuffer.</i>

## -returns

If the operation is successful, the callback function must return STATUS_SUCCESS, or another status value for which NT_SUCCESS(status) equals TRUE. If a capability is not supported, the client driver can return NT_SUCCESS(status) equals FALSE, such as STATUS_UNSUCCESSFUL.

## -remarks

The class extension invokes this callback function implemented by the client driver when the class extension receives a request to determine the emulated controller's capabilities. The callback is invoked only after <a href="/windows-hardware/drivers/ddi/wdfdriver/nc-wdfdriver-evt_wdf_driver_device_add">EvtDriverDeviceAdd</a> has returned, typically in <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_prepare_hardware">EvtDevicePrepareHardware</a>. This callback cannot be invoked after <a href="/windows-hardware/drivers/ddi/wdfdevice/nc-wdfdevice-evt_wdf_device_release_hardware">EvtDeviceReleaseHardware</a> has returned. 

The class extension reports these capability GUIDs, as not supported: 

<ul>
<li>GUID_USB_CAPABILITY_STATIC_STREAMS</li>
<li>GUID_USB_CAPABILITY_CLEAR_TT_BUFFER_ON_ASYNC_TRANSFER_CANCEL</li>
</ul>
The class extension reports the GUID_USB_CAPABILITY_SELECTIVE_SUSPEND capability GUID as supported without even invoking the callback function.

For other GUIDs, the class extension invokes the client driver's implementation, such as GUID_USB_CAPABILITY_CHAINED_MDLS. The client driver is expected to determine support for I/O requests that use a chained MDL. If this capability is supported then, the <b>TransferBufferMdl</b> member of the <a href="/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> contains the request buffer. If chained MDL is not supported, the client driver does not receive <b>TransferBufferMdl</b> values that  point to chained MDLs.

## -see-also

<a href="/windows-hardware/drivers/usbcon/">Architecture: USB Device Emulation (UDE)</a>



<a href="/windows-hardware/drivers/usbcon/">Write a UDE client driver</a>
