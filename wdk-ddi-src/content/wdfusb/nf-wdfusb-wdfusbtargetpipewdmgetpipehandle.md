---
UID: NF:wdfusb.WdfUsbTargetPipeWdmGetPipeHandle
title: WdfUsbTargetPipeWdmGetPipeHandle function (wdfusb.h)
description: The WdfUsbTargetPipeWdmGetPipeHandle method returns the USBD_PIPE_HANDLE-typed handle that is associated with a specified framework pipe object.
old-location: wdf\wdfusbtargetpipewdmgetpipehandle.htm
tech.root: wdf
ms.assetid: d24577e3-3124-4ce7-a6ea-bed75ff18a1e
ms.date: 02/26/2018
ms.keywords: DFUsbRef_4dc66ce5-f27f-4d35-bcea-0efb60a1de3c.xml, WdfUsbTargetPipeWdmGetPipeHandle, WdfUsbTargetPipeWdmGetPipeHandle method, kmdf.wdfusbtargetpipewdmgetpipehandle, wdf.wdfusbtargetpipewdmgetpipehandle, wdfusb/WdfUsbTargetPipeWdmGetPipeHandle
ms.topic: function
f1_keywords:
 - "wdfusb/WdfUsbTargetPipeWdmGetPipeHandle"
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 1.0
req.umdf-ver: 
req.ddi-compliance: DriverCreate, KmdfIrql, KmdfIrql2, UsbKmdfIrql, UsbKmdfIrql2
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
- WdfUsbTargetPipeWdmGetPipeHandle
product:
- Windows
targetos: Windows
req.typenames: 
---

# WdfUsbTargetPipeWdmGetPipeHandle function


## -description


<p class="CCE_Message">[Applies to KMDF only]</p>

The <b>WdfUsbTargetPipeWdmGetPipeHandle</b> method returns the USBD_PIPE_HANDLE-typed handle that is associated with a specified framework pipe object. 


## -parameters




### -param UsbPipe [in]

A handle to a framework pipe object that was obtained by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>.


## -returns



<b>WdfUsbTargetPipeWdmGetPipeHandle</b> returns a USBD_PIPE_HANDLE-typed handle. 

A bug check occurs if the driver supplies an invalid object handle.






## -remarks



A framework-based driver needs to obtain a USBD_PIPE_HANDLE-typed handle only if it creates a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a> that requires a pipe handle.

The driver can call the <b>WdfUsbTargetPipeWdmGetPipeHandle</b> method after it has called <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>. The USBD_PIPE_HANDLE-typed handle that <b>WdfUsbTargetPipeWdmGetPipeHandle</b> returns is valid until the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again, the driver calls <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbinterfaceselectsetting">WdfUsbInterfaceSelectSetting</a>, or the framework pipe object is deleted. If the driver provides an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfobject/nc-wdfobject-evt_wdf_object_context_cleanup">EvtCleanupCallback</a> function for the framework pipe object, and if the object is deleted before the driver calls <b>WdfUsbTargetDeviceSelectConfig</b> again or calls <b>WdfUsbInterfaceSelectSetting</b>, the handle is valid until the object's <i>EvtCleanupCallback</i> function returns.

For more information about the <b>WdfUsbTargetPipeWdmGetPipeHandle</b> method and USB I/O targets, see <a href="https://docs.microsoft.com/windows-hardware/drivers/wdf/usb-i-o-targets">USB I/O Targets</a>.


#### Examples

The following code example obtains the USBD_PIPE_HANDLE-typed handle for a specified pipe.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>USBD_PIPE_HANDLE  usbdPipeHandle;

usbdPipeHandle = WdfUsbTargetPipeWdmGetPipeHandle(UsbPipe);</pre>
</td>
</tr>
</table></span></div>



## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb">URB</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbinterfacegetconfiguredpipe">WdfUsbInterfaceGetConfiguredPipe</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/wdfusb/nf-wdfusb-wdfusbtargetdeviceselectconfig">WdfUsbTargetDeviceSelectConfig</a>
 

 

