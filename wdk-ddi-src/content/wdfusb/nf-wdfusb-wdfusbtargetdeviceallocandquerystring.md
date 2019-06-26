---
UID: NF:wdfusb.WdfUsbTargetDeviceAllocAndQueryString
title: WdfUsbTargetDeviceAllocAndQueryString function (wdfusb.h)
description: The WdfUsbTargetDeviceAllocAndQueryString method allocates a buffer, then it retrieves the Unicode string that is associated with a specified USB device and descriptor index value.
old-location: wdf\wdfusbtargetdeviceallocandquerystring.htm
tech.root: wdf
ms.assetid: a9dea258-601b-4ff7-b03b-b3f22d86f314
ms.date: 02/26/2018
ms.keywords: DFUsbRef_708583a1-a585-402f-afd6-5df4457b0a25.xml, WdfUsbTargetDeviceAllocAndQueryString, WdfUsbTargetDeviceAllocAndQueryString method, kmdf.wdfusbtargetdeviceallocandquerystring, wdf.wdfusbtargetdeviceallocandquerystring, wdfusb/WdfUsbTargetDeviceAllocAndQueryString
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
- WdfUsbTargetDeviceAllocAndQueryString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceAllocAndQueryString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]</p>

The <b>WdfUsbTargetDeviceAllocAndQueryString</b> method allocates a buffer, then it retrieves the Unicode string that is associated with a specified USB device and descriptor index value.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param StringMemoryAttributes [in, optional]

A pointer to a caller-allocated <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains caller-supplied attributes for the new memory object. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param StringMemory [out]

A pointer to a location that receives a handle to the memory object that contains the Unicode string. The string is NULL-terminated only if the device supplies a NULL-terminated string. 


### -param NumCharacters [out, optional]

A pointer to a location that receives the number of characters that are contained in the string descriptor. If the Unicode string is NULL-terminated, this number includes the NULL character. This parameter is optional and can be <b>NULL</b>.


### -param StringIndex [in]

An index value that identifies the Unicode string. This index value is obtained from a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a> structure.


### -param LangID [in, optional]

A language identifier. The Unicode string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification. 


## -returns



<b>WdfUsbTargetDeviceAllocAndQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
An invalid parameter was detected.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
A memory buffer could not be allocated.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_DEVICE_DATA_ERROR</b></dt>
</dl>
</td>
<td width="60%">
The USB device returned an invalid descriptor.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_BUFFER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The supplied buffer was too small.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



The <b>WdfUsbTargetDeviceAllocAndQueryString</b> method, which your driver only needs to call once to obtain a string descriptor, is an alternative to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicequerystring">WdfUsbTargetDeviceQueryString</a> method, which must be called twice to obtain a string.

The method locates the specified USB string descriptor, copies the Unicode string from the descriptor into a memory object, and returns a handle to the memory object. 

After calling <b>WdfUsbTargetDeviceAllocAndQueryString</b>, your driver can pass the <i>StringMemory</i> handle to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a> to access the contents of the memory object.

For more information about USB string descriptors, see the USB specification.

For more information about the <b>WdfUsbTargetDeviceAllocAndQueryString</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example calls <b>WdfUsbTargetDeviceAllocAndQueryString</b> to obtain a manufacturer's name string, in USA English (0x0409), from a USB device descriptor. (The driver previously stored the descriptor in driver-defined context space.)

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PMY_DEVICE_CONTEXT  myDeviceContext;
WDFMEMORY  memoryHandle;
USHORT  numCharacters;

myDeviceContext = GetDeviceContext(device);

status = WdfUsbTargetDeviceAllocAndQueryString(
                                        myDeviceContext->UsbTargetDevice,
                                        WDF_NO_OBJECT_ATTRIBUTES,
                                        &memoryHandle,
                                        &numCharacters,
                                        myDeviceContext->UsbDeviceDescr.iManufacturer,
                                        0x0409
                                        );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_configuration_descriptor">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_device_descriptor">USB_DEVICE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbspec/ns-usbspec-_usb_interface_descriptor">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdevicequerystring">WdfUsbTargetDeviceQueryString</a>
 

 

