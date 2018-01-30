---
UID: NF:usbdlib.USBD_IsochUrbAllocate
title: USBD_IsochUrbAllocate function
author: windows-driver-content
description: The USBD_IsochUrbAllocate routine allocates and formats a URB structure for an isochronous transfer request.
old-location: buses\usbd_isochurballocate.htm
old-project: usbref
ms.assetid: 357FB967-C9D8-468C-AA14-4EF071D55D7B
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: usbdlib/USBD_IsochUrbAllocate, USBD_IsochUrbAllocate, USBD_IsochUrbAllocate routine [Buses], buses.usbd_isochurballocate
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: usbdlib.h
req.include-header: 
req.target-type: Desktop
req.target-min-winverclnt: Requires WDK for Windows 8. Targets Windows Vista and later versions of the Windows operating system.
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
req.lib: Usbdex.lib
req.dll: 
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	LibDef
apilocation:
-	Usbdex.lib
-	Usbdex.dll
apiname:
-	USBD_IsochUrbAllocate
product: Windows
targetos: Windows
req.typenames: "*PUSBCAMD_DEVICE_DATA2, USBCAMD_DEVICE_DATA2"
req.product: Windows 10 or later.
---

# USBD_IsochUrbAllocate function


## -description


The  <b>USBD_IsochUrbAllocate</b> routine allocates and formats a <a href="..\usb\ns-usb-_urb.md">URB</a> structure for an isochronous transfer request.



<b>Note for Windows Driver Framework (WDF) Drivers:  </b>If your client driver is a WDF-based driver, then you must call the <a href="..\wdfusb\nf-wdfusb-wdfusbtargetdevicecreateisochurb.md">WdfUsbTargetDeviceCreateIsochUrb</a> method instead of <b>USBD_IsochUrbAllocate</b> to allocate memory for the <a href="..\usb\ns-usb-_urb.md">URB</a> structure.


## -syntax


````
NTSTATUS USBD_IsochUrbAllocate(
  _In_  USBD_HANDLE   USBDHandle,
  _In_  ULONG         NumberOfIsochPacket,
  _Out_ PURB        *Urb
);
````


## -parameters




### -param USBDHandle [in]

USBD handle that is retrieved by the client driver in a previous call to  the <a href="..\usbdlib\nf-usbdlib-usbd_createhandle.md">USBD_CreateHandle</a> routine.


### -param NumberOfIsochPacket [in]

Specifies the maximum number of isochronous packets required to perform the transfer. The transfer buffer is described in a variable-length array of <a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a> structures that stores information about each packet, such as byte offset of the packet within the buffer. The array is specified in the <b>IsoPacket</b> member of the <a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a> structure, which is used to define the format of an isochronous request URB.


### -param Urb [out]

Pointer to an <a href="..\usb\ns-usb-_urb.md">URB</a> structure,  which receives the URB allocated by <b>USBD_IsochUrbAllocate</b>. All members of the URB structure are set to zero. The allocated URB is large enough to hold the  maximum number of isochronous packets indicated by <b>NumberOfIsochPacket</b>. 

The client driver must free the URB when the driver has finished using it by calling <a href="..\usbdlib\nf-usbdlib-usbd_urbfree.md">USBD_UrbFree</a>.


## -returns


The <b>USBD_IsochUrbAllocate</b> routine returns STATUS_SUCCESS if the request is successful. Otherwise,  <a href="..\usbdlib\nf-usbdlib-usbd_urballocate.md">USBD_UrbAllocate</a> sets <i>Urb</i> to NULL and returns an NT status failure code. 

Possible values include, but are not limited to, STATUS_INVALID_PARAMETER, which  indicates the caller passed in NULL to <i>USBDHandle</i> or <i>Urb</i>.



## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/hh450844">Allocating and Building URBs</a>

<a href="..\usb\ns-usb-_urb_isoch_transfer.md">_URB_ISOCH_TRANSFER</a>

<a href="..\usb\ns-usb-_usbd_iso_packet_descriptor.md">USBD_ISO_PACKET_DESCRIPTOR</a>

<a href="https://msdn.microsoft.com/library/windows/hardware/hh406225">How to Transfer Data to USB Isochronous Endpoints</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBD_IsochUrbAllocate routine%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

