---
UID: NF:wdfusb.WdfUsbTargetDeviceCreateUrb
title: WdfUsbTargetDeviceCreateUrb function (wdfusb.h)
description: The WdfUsbTargetDeviceCreateUrb method allocates a USB request block (URB).
old-location: wdf\wdfusbtargetdevicecreateurb.htm
tech.root: wdf
ms.assetid: 274232FF-573A-47B4-B363-2FA7F810BF84
ms.date: 02/26/2018
ms.keywords: WdfUsbTargetDeviceCreateUrb, WdfUsbTargetDeviceCreateUrb method, kmdf.wdfusbtargetdevicecreateurb, wdf.wdfusbtargetdevicecreateurb, wdfusb/WdfUsbTargetDeviceCreateUrb
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbTargetDeviceCreateUrb"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 
req.ddi-compliance: DriverCreate
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: Wdf01000.sys (see Framework Library Versioning.)
req.dll: 
req.irql: <=DISPATCH_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- LibDef
api_location:
- Wdf01000.sys
- Wdf01000.sys.dll
api_name:
- WdfUsbTargetDeviceCreateUrb
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetDeviceCreateUrb function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>


   The 
  <b>WdfUsbTargetDeviceCreateUrb</b> method allocates a USB request block (URB).


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Attributes [in, optional]

A pointer to a caller-supplied <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/ns-wdfobject-_wdf_object_attributes">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new memory object.   If the driver provides this parameter, the structure's <b>ParentObject</b> member must be a USB device object (WDFUSBDEVICE) or a request object (WDFREQUEST) created by the framework, or any object whose chain of parents leads to one of these types. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param UrbMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object.


### -param Urb [out, optional]

A pointer to an URB structure that receives the address of the newly allocated URB. This parameter is optional and can be NULL.


## -returns



<b>WdfUsbTargetDeviceCreateUrb</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
<dt><b>STATUS_INVALID_DEVICE_STATE</b></dt>
</dl>
</td>
<td width="60%">
The driver did not specify a client contract version when it called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_create_config_init">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
There was insufficient memory to create a new URB.

</td>
</tr>
</table>
 

This method also might return other <a href="https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values">NTSTATUS values</a>.




## -remarks



Before calling <b>WdfUsbTargetDeviceCreateUrb</b>, a driver must call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>. If successful, <b>WdfUsbTargetDeviceCreateUrb</b> returns a handle to a framework memory object that describes the newly allocated URB. Typically, a driver calls <b>WdfUsbTargetDeviceCreateUrb</b> from within a <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

A driver can call <b>WdfUsbTargetDeviceCreateUrb</b> to allocate an URB structure before calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>.

<b>WdfUsbTargetDeviceCreateUrb</b> is similar in operation to  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorycreate">WdfMemoryCreate</a>. Both methods allocate a framework memory object, and both methods also provide the option of receiving the buffer (in this case, the URB) associated with the memory object. In both cases, the caller can also retrieve the buffer later by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfmemory/nf-wdfmemory-wdfmemorygetbuffer">WdfMemoryGetBuffer</a>.

If the driver provides an <i>Urb</i> parameter when it calls <b>WdfUsbTargetDeviceCreateUrb</b>, you can format the URB manually or by calling the UsbBuildXxx routines.

The memory object and its buffer are deleted when the parent object is deleted. A driver can also delete a memory object and its buffer by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfobject/nf-wdfobject-wdfobjectdelete">WdfObjectDelete</a>.


#### Examples

The following code example declares a framework memory object. The example calls <b>WdfUsbTargetDeviceCreateUrb</b> to allocate a USB request block, and then calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a> to format a request that uses the URB structure's contents. Finally, the example registers a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfrequest/nc-wdfrequest-evt_wdf_request_completion_routine">CompletionRoutine</a> callback function and sends the request to an I/O target.


```cpp
WDFMEMORY memory;
PURB urb = NULL;

WDF_OBJECT_ATTRIBUTES_INIT(&objectAttribs);
objectAttribs.ParentObject = UsbDevice;

status = WdfUsbTargetDeviceCreateUrb(
    pDevContext->WdfUsbTargetDevice,
    &objectAttribs,
    &memory,
    &urb);

status = WdfUsbTargetDeviceFormatRequestForUrb(
    deviceContext->WdfUsbTargetDevice,
    request,
    memory,
    NULL);

WdfRequestSetCompletionRoutine(
    request,
    MyCompletionRoutine,
    NULL);

if (!WdfRequestSend(
        request,
        WdfUsbTargetDeviceGetIoTarget(UsbDevice),
        NULL)) {
    status = WdfRequestGetStatus(request);
}

```



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdf_usb_device_create_config_init">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreateisochurb">WdfUsbTargetDeviceCreateIsochUrb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdevicecreatewithparameters">WdfUsbTargetDeviceCreateWithParameters</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdfusb/nf-wdfusb-wdfusbtargetdeviceformatrequestforurb">WdfUsbTargetDeviceFormatRequestForUrb</a>
 

 

