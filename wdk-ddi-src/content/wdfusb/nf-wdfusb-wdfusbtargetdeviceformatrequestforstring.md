---
UID: NF:wdfusb.WdfUsbTargetDeviceFormatRequestForString
title: WdfUsbTargetDeviceFormatRequestForString function
author: windows-driver-content
description: The WdfUsbTargetDeviceFormatRequestForString method builds a request for the USB string descriptor that is associated with a USB device's string index value.
old-location: wdf\wdfusbtargetdeviceformatrequestforstring.htm
old-project: wdf
ms.assetid: f1875578-33c1-4d9e-865b-f1f5391f4aca
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: DFUsbRef_ff5bebaa-3db1-4f9a-bac4-2e5e5c297d03.xml, WdfUsbTargetDeviceFormatRequestForString, WdfUsbTargetDeviceFormatRequestForString method, kmdf.wdfusbtargetdeviceformatrequestforstring, wdf.wdfusbtargetdeviceformatrequestforstring, wdfusb/WdfUsbTargetDeviceFormatRequestForString
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
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, RequestFormattedValid, RequestForUrbXrb, RequestSendAndForgetNoFormatting, RequestSendAndForgetNoFormatting2, UsbKmdfIrql, UsbKmdfIrql2
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (KMDF); WUDFx02000.dll (UMDF)
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
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
-	WdfUsbTargetDeviceFormatRequestForString
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceFormatRequestForString function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]

The <b>WdfUsbTargetDeviceFormatRequestForString</b> method builds a request for the USB string descriptor that is associated with a USB device's string index value. 


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Request [in]

A handle to a framework request object.


### -param Memory [in]

A handle to a framework memory object.


### -param Offset [in, optional]

A pointer to a caller-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a> structure that supplies optional byte offset and length values. The framework uses these values to determine the beginning address and length, within the output buffer, for storing the string descriptor. If this pointer is <b>NULL</b>, the descriptor is stored at the beginning of the output buffer, and the maximum string length is the buffer length. 


### -param StringIndex [in]

An index value that identifies the string. This index value is obtained from a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>, <a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>, or <a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a> structure.


### -param LangID [in, optional]

A language identifier. The string will be retrieved for the language that this identifier specifies. For information about obtaining a device's supported language identifiers, see the USB specification. 


## -returns



<b>WdfUsbTargetDeviceFormatRequestForString</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
The buffer's byte count was not an even number.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INTEGER_OVERFLOW</b></dt>
</dl>
</td>
<td width="60%">
The offset that <i>Offset</i> specifies was invalid.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



After <b>WdfUsbTargetDeviceFormatRequestForString</b> returns, the driver must call <a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a> to send the request. After <b>WdfRequestSend</b> returns, the driver can pass the <i>Memory</i> handle to <a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a> to obtain a pointer to the memory buffer. The buffer will contain a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540147">USB_STRING_DESCRIPTOR</a> structure that describes the string descriptor.

For more information about the <b>WdfUsbTargetDeviceFormatRequestForString</b> method and USB I/O targets, see <a href="https://msdn.microsoft.com/195c0f4b-7f33-428a-8de7-32643ad854c6">USB I/O Targets</a>.


#### Examples

The following code example creates a request object and a memory object, and it passes the object handles to <b>WdfUsbTargetDeviceFormatRequestForString</b>. Then, the example sets a <a href="https://msdn.microsoft.com/7d3eb4d6-9fc7-4924-9b95-f5824713049b">CompletionRoutine</a> callback function for the request and sends the request to an I/O target.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>NTSTATUS status;
PDEVICE_CONTEXT  deviceContext = GetDeviceContext(device);
WDFREQUEST  request;
WDFMEMORY  memHandle;
WDF_OBJECT_ATTRIBUTES  attributes;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;attributes);

status = WdfRequestCreate(
                          &amp;attributes,
                          WdfUsbTargetDeviceGetIoTarget(deviceContext-&gt;UsbTargetDevice),
                          &amp;request
                          );

if (!NT_SUCCESS(status)){
    return status;
}
status = WdfMemoryCreate(
                         WDF_NO_OBJECT_ATTRIBUTES,
                         NonPagedPool,
                         0,
                         STR_DESC_STRING_SIZE,
                         &amp;memHandle,
                         NULL
                         );
if (!NT_SUCCESS(status)){
    WdfObjectDelete(request);
    return status;
}
status = WdfUsbTargetDeviceFormatRequestForString(
                         deviceContext-&gt;UsbTargetDevice,
                         request,
                         memHandle,
                         NULL,
                         deviceContext-&gt;UsbDeviceDescr.iManufacturer,
                         0x0409
                         );
if (NT_SUCCESS(status)) {
    WdfRequestSetCompletionRoutine(
                                   request,
                                   MyCompletionRoutine,
                                   NULL
                                   );

    if (WdfRequestSend(
                       request,
                       WdfUsbTargetDeviceGetIoTarget(deviceContext-&gt;UsbTargetDevice),
                       NULL
                       )) {
        status = STATUS_PENDING;
    }
}
else {
    WdfObjectDelete(memHandle);
    WdfObjectDelete(request);
    return status;
}</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539241">USB_CONFIGURATION_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff539280">USB_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540065">USB_INTERFACE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540147">USB_STRING_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/Ff548718">WDFMEMORY_OFFSET</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff548715">WdfMemoryGetBuffer</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550027">WdfRequestSend</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550030">WdfRequestSetCompletionRoutine</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff550074">WdfUsbTargetDeviceAllocAndQueryString</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439428">WdfUsbTargetDeviceCreateWithParameters</a>
 

 

