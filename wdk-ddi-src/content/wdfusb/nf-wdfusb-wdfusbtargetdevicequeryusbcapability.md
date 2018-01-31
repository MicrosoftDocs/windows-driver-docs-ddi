---
UID: NF:wdfusb.WdfUsbTargetDeviceQueryUsbCapability
title: WdfUsbTargetDeviceQueryUsbCapability function
author: windows-driver-content
description: The WdfUsbTargetDeviceQueryUsbCapability method determines whether the host controller and USB driver stack support a specific capability.
old-location: wdf\wdfusbtargetdevicequeryusbcapability.htm
old-project: wdf
ms.assetid: B6C3E94F-AFC9-45EC-91F1-F0E3586DBDA1
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: wdf.wdfusbtargetdevicequeryusbcapability, WdfUsbTargetDeviceQueryUsbCapability method, PFN_WDFUSBTARGETDEVICEQUERYUSBCAPABILITY, wdfusb/WdfUsbTargetDeviceQueryUsbCapability, kmdf.wdfusbtargetdevicequeryusbcapability, WdfUsbTargetDeviceQueryUsbCapability
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: wdfusb.h
req.include-header: Wdfusb.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
req.target-min-winversvr: 
req.kmdf-ver: 1.11
req.umdf-ver: 2.0
req.ddi-compliance: DriverCreate
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
-	WdfUsbTargetDeviceQueryUsbCapability
product: Windows
targetos: Windows
req.typenames: WDF_USB_REQUEST_TYPE, *PWDF_USB_REQUEST_TYPE
req.product: Windows 10 or later.
---

# WdfUsbTargetDeviceQueryUsbCapability function


## -description


<p class="CCE_Message">[Applies to KMDF and UMDF]


   The <b>WdfUsbTargetDeviceQueryUsbCapability</b> method determines whether the host controller and USB driver stack support a specific capability.


## -syntax


````
NTSTATUS WdfUsbTargetDeviceQueryUsbCapability(
  _In_            WDFUSBDEVICE UsbDevice,
  _In_      const PGUID        *CapabilityType,
  _In_            ULONG        CapabilityBufferLength,
  _Out_opt_       PVOID        CapabilityBuffer,
  _Out_opt_       PULONG       ResultLength
);
````


## -parameters




#### - UsbDevice [in]

A handle to a USB device object.


#### - CapabilityType [in]

A pointer to a GUID that represents the capability about which the client driver wants to retrieve information. The possible  <i>PGUID</i>  values are  as follows:
<ul>
<li>GUID_USB_CAPABILITY_CHAINED_MDLS</li>
<li>GUID_USB_CAPABILITY_STATIC_STREAMS</li>
<li>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</li>
<li>GUID_USB_CAPABILITY_FUNCTION_SUSPEND

</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</li>
<li>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</li>
</ul>See more information in Remarks.


#### - CapabilityBufferLength [in]

Length, in bytes, of the buffer pointed to by <i>CapabilityBuffer</i>.


#### - CapabilityBuffer [out, optional]

A pointer to a caller-allocated buffer to receive the requested USB capability. This parameter is optional. If 
                       <i>CapabilityBufferLength</i> is zero, this parameter must be NULL. Similarly, if <i>CapabilityBufferLength</i> is nonzero, this parameter must be supplied. This parameter corresponds to the <i>OutputBuffer</i> parameter of the <a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a> routine.


#### - ResultLength [out, optional]

A pointer to a location containing the size, in bytes, of the returned capability. This parameter is optional.


## -returns


<b>WdfUsbTargetDeviceQueryUsbCapability</b> returns STATUS_SUCCESS if the operation succeeds. Otherwise, this method can return one of the following values:
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
The USB device object handle is not valid.

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
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
The caller passed an invalid parameter value.

<ul>
<li><i>UsbDevice</i> or  <i>CapabilityType</i> is NULL.</li>
<li><i>CapabilityBuffer</i> is NULL but <i>CapabilityBufferLength</i> contains a nonzero value. Conversely, the caller provided a <i>CapabilityBuffer</i> but <i>CapabilityBufferLength</i> is zero.</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_IMPLEMENTED</b></dt>
</dl>
</td>
<td width="60%">
The specified capability is not supported by the underlying USB driver stack.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
The specified capability is not supported by the host controller hardware.

</td>
</tr>
</table> 

This method also might return other <a href="https://msdn.microsoft.com/library/windows/hardware/ff557697">NTSTATUS values</a>.



## -remarks


Before calling <b>WdfUsbTargetDeviceQueryUsbCapability</b>, the driver must call  <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreatewithparameters.md">WdfUsbTargetDeviceCreateWithParameters</a> to register with the underlying USB driver stack.

<b>WdfUsbTargetDeviceQueryUsbCapability</b> must be called after the driver's <a href="..\wdfdevice\nc-wdfdevice-evt_wdf_device_prepare_hardware.md">EvtDevicePrepareHardware</a> callback function has been called. 

The following table describes the USB-specific capabilities that a KMDF-based USB client driver can query through a <b>WdfUsbTargetDeviceQueryUsbCapability</b> call. 
<table>
<tr>
<th>Capability GUID</th>
<th>Description</th>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_CHAINED_MDLS</td>
<td>
The new USB driver stack in Windows 8 is capable of accepting a chained MDL (see <a href="..\wdm\ns-wdm-_mdl.md">MDL</a>) from the a KMDF-based USB client driver.

 For more information about the chained MDLs capability in the USB driver stack, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450848">How to Send Chained MDLs</a>.  

This GUID applies to KMDF drivers only.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_STATIC_STREAMS</td>
<td>
 Whereas USB 2.0 and earlier supports sending only a single data stream through a bulk endpoint, USB 3.0 permits sending and receiving multiple data streams through a bulk endpoint. 


For more information about opening streams, see <a href="https://msdn.microsoft.com/library/windows/hardware/hh450846">How to Open and Close Static Streams in a USB Bulk Endpoint</a>.

This GUID applies to KMDF drivers only.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_FUNCTION_SUSPEND</td>
<td>
The Universal Serial Bus (USB) 3.0 specification defines a new feature called function suspend. The feature enables an individual function of a composite device to enter a low-power state, independently of other functions. 

For more information about function suspend, see <a href="https://msdn.microsoft.com/91F96D30-CD18-4DDC-BA5A-7BFFA8FBED9B">How to Implement Function Suspend in a Composite Driver</a>.

This GUID applies to KMDF drivers only.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_SELECTIVE_SUSPEND</td>
<td>
For information about selective suspend, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540144">USB Selective Suspend</a>.

This GUID applies to KMDF drivers only.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_DEVICE_CONNECTION_HIGH_SPEED_COMPATIBLE</td>
<td>
Determines whether the bus is operating at high-speed or higher. 

This GUID applies to KMDF and UMDF drivers.

</td>
</tr>
<tr>
<td>GUID_USB_CAPABILITY_DEVICE_CONNECTION_SUPER_SPEED_COMPATIBLE</td>
<td>
Determines whether the bus is operating at SuperSpeed or higher.

This GUID applies to KMDF and UMDF drivers.

</td>
</tr>
</table> 



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406230">USBD_QueryUsbCapability</a>

<a href="..\wdfusb\nf-wdfusb-wdfusbtargetdeviceretrieveinformation.md">WdfUsbTargetDeviceRetrieveInformation</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [wdf\wdf]:%20WdfUsbTargetDeviceQueryUsbCapability method%20 RELEASE:%20(1/11/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

