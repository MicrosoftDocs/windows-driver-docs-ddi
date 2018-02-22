---
UID: NF:wdfusb.WdfUsbTargetDeviceCreateIsochUrb
title: WdfUsbTargetDeviceCreateIsochUrb function
author: windows-driver-content
description: The WdfUsbTargetDeviceCreateIsochUrb method allocates an isochronous USB request block (URB).
old-location: wdf\wdfusbtargetdevicecreateisochurb.htm
old-project: wdf
ms.assetid: 2D25A276-A367-4E59-9CA0-4F480675DD77
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: wdf.wdfusbtargetdevicecreateisochurb, WdfUsbTargetDeviceCreateIsochUrb method, WdfUsbTargetDeviceCreateIsochUrb, kmdf.wdfusbtargetdevicecreateisochurb, wdfusb/WdfUsbTargetDeviceCreateIsochUrb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Wdf01000.sys
-	Wdf01000.sys.dll
apiname:
-	WdfUsbTargetDeviceCreateIsochUrb
product: Windows
targetos: Windows
req.typenames: "*PWDF_USB_REQUEST_TYPE, WDF_USB_REQUEST_TYPE"
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceCreateIsochUrb function


## -description


<p class="CCE_Message">[Applies to KMDF only]


   The 
  <b>WdfUsbTargetDeviceCreateIsochUrb</b> method allocates an isochronous USB request block (URB).


## -syntax


````
NTSTATUS WdfUsbTargetDeviceCreateIsochUrb(
  _In_      WDFUSBDEVICE           UsbDevice,
  _In_opt_  PWDF_OBJECT_ATTRIBUTES Attributes,
  _In_      ULONG                  NumberOfIsochPackets,
  _Out_     WDFMEMORY              *UrbMemory,
  _Out_opt_ PURB                   *Urb
);
````


## -parameters




### -param UsbDevice [in]

A handle to a USB device object that was obtained from a previous call to <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>.


### -param Attributes [in, optional]

A pointer to a caller-supplied <a href="..\wdfobject\ns-wdfobject-_wdf_object_attributes.md">WDF_OBJECT_ATTRIBUTES</a> structure that contains attributes for the new memory object.   If the driver provides this parameter, the structure's <b>ParentObject</b> member must be a USB device object (WDFUSBDEVICE) or a request object (WDFREQUEST) created by the framework, or any object whose chain of parents leads to one of these types. This parameter is optional and can be WDF_NO_OBJECT_ATTRIBUTES.


### -param NumberOfIsochPackets [in]

Specifies the number of isochronous packets for which the system allocates memory in the URB.


### -param UrbMemory [out]

A pointer to a WDFMEMORY-typed location that receives a handle to a framework memory object.


### -param Urb [out, optional]

A pointer to an URB structure that receives the address of the new isochronous URB. The framework initializes contents of the URB structure to zero. This parameter is optional and can be NULL.


## -returns



<b>WdfUsbTargetDeviceCreateIsochUrb</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:

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
The driver did not specify a client contract version when it called <a href="..\wdfusb\nf-wdfusb-wdf_usb_device_create_config_init.md">WDF_USB_DEVICE_CREATE_CONFIG_INIT</a>.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
Insufficient memory was available.

</td>
</tr>
</table>
 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.




## -remarks



Before calling <b>WdfUsbTargetDeviceCreateIsochUrb</b>, a driver must call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>. If successful, <b>WdfUsbTargetDeviceCreateIsochUrb</b> returns a handle to a framework memory object that describes the newly allocated isochronous URB.

A driver can call <b>WdfUsbTargetDeviceCreateIsochUrb</b> to allocate a URB structure before calling <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceformatrequestforurb.md">WdfUsbTargetDeviceFormatRequestForUrb</a>.

Typically, a driver calls <b>WdfUsbTargetDeviceCreateIsochUrb</b> from within a <a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/wdf/request-handlers">request handler</a>.

The memory object and its buffer are deleted when the parent object is deleted. A driver can also delete a memory object and its buffer by calling <a href="..\wdfobject\nf-wdfobject-wdfobjectdelete.md">WdfObjectDelete</a>.

For related information, see the Remarks section of <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateurb.md">WdfUsbTargetDeviceCreateUrb</a>.


#### Examples

The following code example is based on the PerformIsochTransfer routine in the Isorwr sample driver. The example calls <b>WdfUsbTargetDeviceCreateIsochUrb</b> to allocate an isochronous USB request block. The example determines the number  of bytes required to hold the isochronous transfer request, and then manually configures the URB header and the isochronous packets in the URB.  At this point, the driver can call <a href="..\wdfusb\nf-wdfusb-wdfusbtargetpipeformatrequestforurb.md">WdfUsbTargetPipeFormatRequestForUrb</a>, as shown in the example in  <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateurb.md">WdfUsbTargetDeviceCreateUrb</a>.

<div class="code"><span codelanguage=""><table>
<tr>
<th></th>
</tr>
<tr>
<td>
<pre>
USBD_PIPE_HANDLE usbdPipeHandle;
ULONG numPackets = UserBufferLength/TransferSizePerFrame;
ULONG urbSize;
PURB urb;  
WDFMEMORY memory;

WDF_OBJECT_ATTRIBUTES_INIT(&amp;objectAttribs);  
objectAttribs.ParentObject = UsbDevice;

status = WdfUsbTargetDeviceCreateIsochUrb(
                                     pDevContext-&gt;WdfUsbTargetDevice,  
                                     &amp;objectAttribs,  
                                     0, 
                                     numPackets, 
                                     &amp;memory,  
                                     NULL  
                                     ); 
 
urb = WdfMemoryGetBuffer(urbMemory, &amp;urbSize); 
urbSize = GET_ISO_URB_SIZE(numPackets);  

usbdPipeHandle = WdfUsbTargetPipeWdmGetPipeHandle(pipe);
urb-&gt;UrbIsochronousTransfer.Hdr.Length = GET_ISO_URB_SIZE(numPackets);  
urb-&gt;UrbIsochronousTransfer.Hdr.Function = URB_FUNCTION_ISOCH_TRANSFER;  
urb-&gt;UrbIsochronousTransfer.PipeHandle = usbdPipeHandle; 

for (packetId = 0; packetId &lt; numberOfPackets; packetId++) {

     Urb-&gt; UrbIsochronousTransfer.IsoPacket[packetId].Offset = xxx;
     Urb-&gt; UrbIsochronousTransfer.IsoPacket[packetId].YYY = yyy;
}

</pre>
</td>
</tr>
</table></span></div>



## -see-also

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateurb.md">WdfUsbTargetDeviceCreateUrb</a>



<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceCreateIsochUrb method%20 RELEASE:%20(2/20/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

