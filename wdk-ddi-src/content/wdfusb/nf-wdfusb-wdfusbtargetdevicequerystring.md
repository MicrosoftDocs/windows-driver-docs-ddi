---
UID: NF:wdfusb.WdfUsbTargetDeviceQueryString
title: WdfUsbTargetDeviceQueryString function
author: windows-driver-content
description: The WdfUsbTargetDeviceQueryString method retrieves the Unicode string that is associated with a specified USB device and descriptor index value.
old-location: wdf\wdfusbtargetdevicequerystring.htm
old-project: wdf
ms.assetid: e7b25a47-e197-4670-9907-409d5aeb5462
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_ea603209-6043-48e6-b8ff-4795f572dea6.xml, WdfUsbTargetDeviceQueryString, WdfUsbTargetDeviceQueryString method, kmdf.wdfusbtargetdevicequerystring, wdf.wdfusbtargetdevicequerystring, wdfusb/WdfUsbTargetDeviceQueryString
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	LibDef
api_location:
-	Wdf01000.sys
-	Wdf01000.sys.dll
-	WUDFx02000.dll
-	WUDFx02000.dll.dll
api_name:
-	WdfUsbTargetDeviceQueryString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceQueryString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceQueryString</b> method retrieves the Unicode string that is associated with a specified USB device and descriptor index value.


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in, optional]

A handle to a framework request object. This parameter is optional and can be <b>NULL</b>. For more information, see the following Remarks section. 


### -param RequestOptions [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a> structure that specifies options for the request. This pointer is optional and can be <b>NULL</b>. For more information, see the following Remarks section. 


### -param String [out, optional]

A pointer to a caller-allocated buffer that receives the requested Unicode string. The string is NULL-terminated only if the device supplies a NULL-terminated string. If this pointer is <b>NULL</b>, <b>WdfUsbTargetDeviceQueryString</b> returns the required buffer size (that is, the required number of Unicode characters) in the location that <i>NumCharacters</i> points to.


### -param NumCharacters [in, out]

A pointer to a caller-allocated variable. The caller supplies the number of Unicode characters that the buffer can hold. When <b>WdfUsbTargetDeviceQueryString</b> returns, the variable receives the number of characters (including the NULL terminator, if supplied) that are in the Unicode string that the <i>String</i> buffer receives. 


### -param StringIndex [in]

An index value that identifies the Unicode string. This index value is obtained from a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structure.


### -param LangID [in, optional]

A language identifier. The Unicode string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification. 


## -returns



<b>WdfUsbTargetDeviceQueryString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



Drivers should call <b>WdfUsbTargetDeviceQueryString</b> twice, by using the following steps:

<ul>
<li>
Set the <i>String</i> pointer to <b>NULL</b>, so that <b>WdfUsbTargetDeviceQueryString</b> will return the required buffer size in the address that the <i>NumCharacters</i> parameter points to.

</li>
<li>
 Allocate buffer space to hold the number of Unicode characters that are in the requested string. For example, a driver might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff544520">ExAllocatePoolWithTag</a> to allocate a buffer, or it might call <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> to create a framework memory object.

</li>
<li>
Call <b>WdfUsbTargetDeviceQueryString</b> again, setting the <i>String</i> value to a pointer to the new buffer and setting <i>NumCharacters</i> to the buffer's length (that is, the number of Unicode characters, not the byte length).

</li>
</ul>
<b>WdfUsbTargetDeviceQueryString</b> locates the specified USB string descriptor and copies the Unicode string from the descriptor into the supplied buffer. 

If your driver specifies a non-<b>NULL</b> value for the <i>Request</i> parameter, the framework uses the specified request object, and another driver thread can call <a href="https://msdn.microsoft.com/library/windows/hardware/ff549941">WdfRequestCancelSentRequest</a>, if necessary, to attempt to cancel the string query request. If the driver specifies a <b>NULL</b> value for <i>Request</i>, the framework uses an internal request object that the driver cannot cancel. 

Your driver can specify a non-<b>NULL</b> <i>RequestOptions</i> parameter, whether the driver provides a non-<b>NULL</b> or a <b>NULL</b> <i>Request</i> parameter. You can, for example, use the <i>RequestOptions</i> parameter to specify a time-out value. 

For more information about USB string descriptors, see the USB specification.

For more information about the <b>WdfUsbTargetDeviceQueryString</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example calls <b>WdfUsbTargetDeviceQueryString</b> to obtain the required buffer size, calls <a href="https://msdn.microsoft.com/library/windows/hardware/ff548706">WdfMemoryCreate</a> to create a memory object and buffer, and then calls <b>WdfUsbTargetDeviceQueryString</b> again to obtain the manufacturer's name string, in USA English (0x0409), from a USB device descriptor. (The driver previously stored the descriptor in driver-defined context space.)

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>PMY_DEVICE_CONTEXT  myDeviceContext;
USHORT  numCharacters;
PUSHORT  stringBuf;
WDFMEMORY  memoryHandle;

myDeviceContext = GetDeviceContext(device);

status = WdfUsbTargetDeviceQueryString(
                                       myDeviceContext-&gt;UsbTargetDevice,
                                       NULL,
                                       NULL,
                                       NULL,
                                       &amp;numCharacters,
                                       myDeviceContext-&gt;UsbDeviceDescr.iManufacturer,
                                       0x0409
                                       );

ntStatus = WdfMemoryCreate(
                           WDF_NO_OBJECT_ATTRIBUTES,
                           NonPagedPool,
                           POOL_TAG,
                           numCharacters * sizeof(WCHAR),
                           &amp;memoryHandle,
                           (PVOID)&amp;stringBuf
                           );
if (!NT_SUCCESS(ntStatus)) {
    return ntStatus;
}
status = WdfUsbTargetDeviceQueryString(
                                       myDeviceContext-&gt;UsbTargetDevice,
                                       NULL,
                                       NULL,
                                       stringBuf,
                                       &amp;numCharacters,
                                       myDeviceContext-&gt;UsbDeviceDescr.iManufacturer,
                                       0x0409
                                       );</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff552491">WDF_REQUEST_SEND_OPTIONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff549941">WdfRequestCancelSentRequest</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550074">WdfUsbTargetDeviceAllocAndQueryString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

