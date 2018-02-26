---
UID: NF:wdfusb.WdfUsbTargetDeviceRetrieveConfigDescriptor
title: WdfUsbTargetDeviceRetrieveConfigDescriptor function
author: windows-driver-content
description: The WdfUsbTargetDeviceRetrieveConfigDescriptor method retrieves the USB configuration descriptor for the USB device that is associated with a specified framework USB device object.
old-location: wdf\wdfusbtargetdeviceretrieveconfigdescriptor.htm
old-project: wdf
ms.assetid: 4d22384d-757a-499d-a82c-ae846a6372cc
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: ",  , C, D, DFUsbRef_6c3748fe-16c0-4151-8cbd-42c5882475eb.xml, R, T, U, W, WdfUsbTargetDeviceRetrieveConfigDescriptor, WdfUsbTargetDeviceRetrieveConfigDescriptor method, a, b, c, d, e, f, g, i, kmdf.wdfusbtargetdeviceretrieveconfigdescriptor, n, o, p, r, s, t, v, wdf.wdfusbtargetdeviceretrieveconfigdescriptor, wdfusb/WdfUsbTargetDeviceRetrieveConfigDescriptor"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
apiname:
-	WdfUsbTargetDeviceRetrieveConfigDescriptor
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceRetrieveConfigDescriptor function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> method retrieves the USB configuration descriptor for the USB device that is associated with a specified framework USB device object.


## -syntax


````
NTSTATUS WdfUsbTargetDeviceRetrieveConfigDescriptor(
  _In_    WDFUSBDEVICE UsbDevice,
  _Out_   PVOID        ConfigDescriptor,
  _Inout_ PUSHORT      ConfigDescriptorLength
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param ConfigDescriptor [out]

A pointer to a caller-allocated buffer that receives a <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by one or more <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> and <a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a> structures. This parameter is optional and can be <b>NULL</b>, in which case <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> returns the required buffer length. For more information, see the following Remarks section.


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
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> method retrieves all of the specified USB device's configuration information (that is, the configuration descriptor plus any interface or endpoint descriptors that might be present). To learn about the format of this information, see the USB specification.

Drivers should call <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> twice, as follows:

<ol>
<li>
Set the <i>ConfigDescriptor</i> pointer to <b>NULL</b>, so that <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> will return the required buffer size in the address that <i>ConfigDescriptorLength</i> points to.

</li>
<li>
Allocate buffer space to hold the configuration information. For example, a driver might call <a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a> to allocate a buffer, or it might call <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> to create a framework memory object.

</li>
<li>
Call <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> again, passing it a pointer to the new buffer and the buffer's size.

</li>
</ol>
After the second call to <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> returns, the buffer that is pointed to by <i>ConfigDescriptor</i> contains a <a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a> structure, followed by one or more <a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a> and <a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a> structures. These latter structures are arranged in the order that is described in the USB specification.

For more information about the <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example calls <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> to obtain the required buffer size, calls <a href="..\wdfmemory\nf-wdfmemory-wdfmemorycreate.md">WdfMemoryCreate</a> to create a memory object and buffer, and then calls <b>WdfUsbTargetDeviceRetrieveConfigDescriptor</b> again to obtain a device's configuration information.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>USHORT  size;
NTSTATUS  ntStatus;
PMY_DEVICE_CONTEXT  myDeviceContext;
PUSB_CONFIGURATION_DESCRIPTOR  configurationDescriptor = NULL;
WDF_OBJECT_ATTRIBUTES  objectAttribs;
WDFMEMORY  memoryHandle;

myDeviceContext = GetDeviceContext(Device);

ntStatus = WdfUsbTargetDeviceRetrieveConfigDescriptor(
                                            myDeviceContext-&gt;WdfUsbTargetDevice,
                                            NULL,
                                            &amp;size
                                            );

if (ntStatus != STATUS_BUFFER_TOO_SMALL) {
    return ntStatus;
}

WDF_OBJECT_ATTRIBUTES_INIT(&amp;objectAttribs);
objectAttribs.ParentObject = myDeviceContext-&gt;WdfUsbTargetDevice;

ntStatus = WdfMemoryCreate(
                           &amp;objectAttribs,
                           NonPagedPool,
                           POOL_TAG,
                           size,
                           &amp;memoryHandle,
                           (PVOID)&amp;configurationDescriptor
                           );
if (!NT_SUCCESS(ntStatus)) {
    return ntStatus;
}

ntStatus = WdfUsbTargetDeviceRetrieveConfigDescriptor(
                                            myDeviceContext-&gt;WdfUsbTargetDevice,
                                            configurationDescriptor,
                                            &amp;size
                                            );
if (!NT_SUCCESS(ntStatus)) {
    return ntStatus;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\usbspec\ns-usbspec-_usb_configuration_descriptor.md">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="..\usbspec\ns-usbspec-_usb_endpoint_descriptor.md">USB_ENDPOINT_DESCRIPTOR</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicegetdevicedescriptor.md">WdfUsbTargetDeviceGetDeviceDescriptor</a>



<a href="..\wdm\nf-wdm-exallocatepoolwithtag.md">ExAllocatePoolWithTag</a>



<a href="..\usbspec\ns-usbspec-_usb_interface_descriptor.md">USB_INTERFACE_DESCRIPTOR</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceRetrieveConfigDescriptor method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

