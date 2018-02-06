---
UID: NF:usbdlib.UsbBuildGetStatusRequest
title: UsbBuildGetStatusRequest macro
author: windows-driver-content
description: The UsbBuildGetStatusRequest macro formats an URB to obtain status from a device, interface, endpoint, or other device-defined target on a USB device.
old-location: buses\usbbuildgetstatusrequest.htm
old-project: usbref
ms.assetid: 7a5fcb4f-fc9a-4ebb-93ef-b83461557b22
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbfunc_a99bf737-8bb6-4000-af2b-ac076a4ffc8e.xml, UsbBuildGetStatusRequest routine [Buses], UsbBuildGetStatusRequest, buses.usbbuildgetstatusrequest, usbdlib/UsbBuildGetStatusRequest
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: macro
req.header: usbdlib.h
req.include-header: Usbdlib.h
req.target-type: Desktop
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: usbdlib.h
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	usbdlib.h
apiname:
-	UsbBuildGetStatusRequest
product: Windows
targetos: Windows
req.typenames: "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product: Windows 10 or later.
---

# UsbBuildGetStatusRequest macro


## -description



   The <b>UsbBuildGetStatusRequest</b> macro formats an <a href="..\usb\ns-usb-_urb.md">URB</a> to obtain status from a device, interface, endpoint, or other device-defined target on a USB device.


## -syntax


````
void UsbBuildGetStatusRequest(
  _Inout_         Urb,
  _In_     USHORT Op,
  _In_     USHORT Index,
  _In_opt_ PVOID  TransferBuffer,
  _In_opt_ PMDL   TransferBufferMDL,
  _In_     PURB   Link
);
````


## -parameters




### -param urb

TBD


### -param op

TBD


### -param index

TBD


### -param transferBuffer

TBD


### -param transferBufferMDL

TBD


### -param link

TBD




#### - Urb [in, out]

Pointer to an <a href="..\usb\ns-usb-_urb.md">URB</a> to be formatted as an status request.


#### - Op [in]

Specifies one of the following values:




#### URB_FUNCTION_GET_STATUS_FROM_DEVICE

Retrieves status from a USB device.


#### URB_FUNCTION_GET_STATUS_FROM_INTERFACE

Retrieves status from an interface on a USB device.


#### URB_FUNCTION_GET_STATUS_FROM_ENDPOINT

Retrieves status from an endpoint for an interface on a USB device.


#### URB_FUNCTION_GET_STATUS_FROM_OTHER

Retrieves status from a device-defined target on a USB device.


#### - Index [in]

Specifies the device-defined index, returned by a successful configuration request, if the request is for an endpoint or interface. Otherwise, <i>Index</i> must be zero.


#### - TransferBuffer [in, optional]

Pointer to a resident buffer to receive the status data or is <b>NULL</b> if an MDL is supplied in <i>TransferBufferMDL</i>.


#### - TransferBufferMDL [in, optional]

Pointer to an MDL that describes a resident buffer to receive the status data or is <b>NULL</b> if a buffer is supplied in <i>TransferBuffer</i>.


#### - Link [in]

Reserved. Must be set to <b>NULL</b>. 


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>

<a href="..\usb\ns-usb-_urb_control_get_status_request.md">_URB_CONTROL_GET_STATUS_REQUEST</a>

<a href="..\usb\ns-usb-_urb.md">URB</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20UsbBuildGetStatusRequest routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

