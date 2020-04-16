---
UID: NF:wdfusb.WdfUsbTargetDeviceRetrieveConfigDescriptor
title: WdfUsbTargetDeviceRetrieveConfigDescriptor function (wdfusb.h)
description: The WdfUsbTargetDeviceRetrieveConfigDescriptor method retrieves the USB configuration descriptor for the USB device that is associated with a specified framework USB device object.
old-location: wdf\wdfusbtargetdeviceretrieveconfigdescriptor.htm
tech.root: wdf
ms.assetid: 4d22384d-757a-499d-a82c-ae846a6372cc
ms.date: 02/26/2018
keywords: ["WdfUsbTargetDeviceRetrieveConfigDescriptor function"]
ms.keywords: DFUsbRef_6c3748fe-16c0-4151-8cbd-42c5882475eb.xml, WdfUsbTargetDeviceRetrieveConfigDescriptor, WdfUsbTargetDeviceRetrieveConfigDescriptor method, kmdf.wdfusbtargetdeviceretrieveconfigdescriptor, wdf.wdfusbtargetdeviceretrieveconfigdescriptor, wdfusb/WdfUsbTargetDeviceRetrieveConfigDescriptor
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceRetrieveConfigDescriptor"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
- WUDFx02000.dll
- WUDFx02000.dll.dll
api_name:
- WdfUsbTargetDeviceRetrieveConfigDescriptor
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceRetrieveConfigDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> method retrieves the USB configuration descriptor for the USB device that is associated with a specified framework USB device object.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param ConfigDescriptor [out]

A pointer to a caller-allocated buffer that receives a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a> structures. This parameter is optional and can be <b>NULL</b>, in which case <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> returns the required buffer length. For more information, see the following Remarks section.


### -param ConfigDescriptorLength [in, out]

A pointer to a location that supplies the length of the buffer that <i>ConfigDescriptor</i> points to. If the pointer that is supplied for <i>ConfigDescriptor</i> is <b>NULL</b>, <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> returns the required buffer length at the location that is pointed to by <i>ConfigDescriptorLength</i>.


## -returns



<b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
A configuration descriptor was not available for the specified target.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_TOO_SMALL</b></dt>
</dl>
</td>
<td width="60%">
The specified buffer size was too small for the data, or the caller supplied <b>NULL</b> for the <i>ConfigDescriptor</i> parameter.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> method retrieves all of the specified USB device's configuration information (that is, the configuration descriptor plus any interface or endpoint descriptors that might be present). To learn about the format of this information, see the USB specification.

You can use [**WdfUsbTargetDeviceSelectConfig**](nf-wdfusb-wdfusbtargetdeviceselectconfig.md) to select only the first USB configuration listed in the descriptor list, but you can select multiple interfaces within this single configuration. 

Drivers should call <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> twice, as follows:

<ol>
<li>
Set the <i>ConfigDescriptor</i> pointer to <b>NULL</b>, so that <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> will return the required buffer size in the address that <i>ConfigDescriptorLength</i> points to.

</li>
<li>
Allocate buffer space to hold the configuration information. For example, a driver might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a> to allocate a buffer, or it might call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> to create a framework memory object.

</li>
<li>
Call <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> again, passing it a pointer to the new buffer and the buffer's size.

</li>
</ol>
After the second call to <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> returns, the buffer that is pointed to by <i>ConfigDescriptor</i> contains a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by one or more <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a> structures. These latter structures are arranged in the order that is described in the USB specification.

For more information about the <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example calls <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> to obtain the required buffer size, calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a> to create a memory object and buffer, and then calls <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> again to obtain a device's configuration information.

```cpp
USHORT  size;
NTSTATUS  ntStatus;
PMY_DEVICE_CONTEXT  myDeviceContext;
PUSB_CONFIGURATION_DESCRIPTOR  configurationDescriptor = NULL;
WDF_OBJECT_ATTRIBUTES  objectAttribs;
WDFMEMORY  memoryHandle;

myDeviceContext = GetDeviceContext(Device);

ntStatus = WdfUsbTargetDeviceRetrieveConfigDescriptor(
                                            myDeviceContext->WdfUsbTargetDevice,
                                            NULL,
                                            &size
                                            );

if (ntStatus != STATUS_BUFFER_TOO_SMALL) {
    return ntStatus;
}

WDF_OBJECT_ATTRIBUTES_INIT(&objectAttribs);
objectAttribs.ParentObject = myDeviceContext->WdfUsbTargetDevice;

ntStatus = WdfMemoryCreate(
                           &objectAttribs,
                           NonPagedPool,
                           POOL_TAG,
                           size,
                           &memoryHandle,
                           (PVOID)&configurationDescriptor
                           );
if (!NT_SUCCESS(ntStatus)) {
    return ntStatus;
}

ntStatus = WdfUsbTargetDeviceRetrieveConfigDescriptor(
                                            myDeviceContext->WdfUsbTargetDevice,
                                            configurationDescriptor,
                                            &size
                                            );
if (!NT_SUCCESS(ntStatus)) {
    return ntStatus;
}
```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-exallocatepoolwithtag">ExAllocatePoolWithTag</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_endpoint_descriptor">USB_ENDPOINT_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicegetdevicedescriptor">WdfUsbTargetDeviceGetDeviceDescriptor</a>
 

 

