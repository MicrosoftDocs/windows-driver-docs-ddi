---
UID: NF:usbdlib.UsbBuildInterruptOrBulkTransferRequest
title: UsbBuildInterruptOrBulkTransferRequest macro
author: windows-driver-content
description: The UsbBuildInterruptOrBulkTransferRequest macro formats an URB to send or receive data on a bulk pipe, or to receive data from an interrupt pipe.
old-location: buses\usbbuildinterruptorbulktransferrequest.htm
old-project: UsbRef
ms.assetid: 2500fa22-b3f9-419d-9e37-5060b83403fb
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: UsbBuildInterruptOrBulkTransferRequest, usbdlib/UsbBuildInterruptOrBulkTransferRequest, usbfunc_ecc1d157-942d-4d0e-9c07-9fef00cd5faf.xml, UsbBuildInterruptOrBulkTransferRequest routine [Buses], buses.usbbuildinterruptorbulktransferrequest
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
-	UsbBuildInterruptOrBulkTransferRequest
product: Windows
targetos: Windows
req.typenames: USBCAMD_DEVICE_DATA2, *PUSBCAMD_DEVICE_DATA2
req.product: Windows 10 or later.
---

# UsbBuildInterruptOrBulkTransferRequest macro


## -description


The <b>UsbBuildInterruptOrBulkTransferRequest</b> macro formats an <a href="..\usb\ns-usb-_urb.md">URB</a> to send or receive data on a bulk pipe, or to receive data from an interrupt pipe.


## -syntax


````
void UsbBuildInterruptOrBulkTransferRequest(
  _Inout_  PURB             urb,
  _In_     USHORT           length,
  _In_     USBD_PIPE_HANDLE pipeHandle,
  _In_opt_ PVOID            transferBuffer,
  _In_opt_ PMDL             transferBufferMDL,
  _In_     ULONG            transferBufferLength,
  _In_     ULONG            transferFlags,
  _In_     PURB             link
);
````


## -parameters




### -param urb [in, out]

Pointer to an <a href="..\usb\ns-usb-_urb.md">URB</a> to be formatted as an interrupt or bulk transfer request.


### -param length [in]

Specifies the size, in bytes, of the <a href="..\usb\ns-usb-_urb.md">URB</a>.


### -param pipeHandle [in]

Specifies the handle for this pipe returned by the HCD when a configuration was selected.


### -param transferBuffer [in, optional]

Pointer to a resident buffer for the transfer or is <b>NULL</b> if an MDL is supplied in <i>TransferBufferMDL</i>. The contents of this buffer depend on the value of <i>TransferFlags</i>. If USBD_TRANSFER_DIRECTION_IN is specified, this buffer will contain data read from the device on return from the HCD. Otherwise, this buffer contains driver-supplied data to be transferred to the device.


### -param transferBufferMDL [in, optional]

Pointer to an MDL that describes a resident buffer or is <b>NULL</b> if a buffer is supplied in <i>TransferBuffer</i>. The contents of the buffer depend on the value of <i>TransferFlags</i>. If USBD_TRANSFER_DIRECTION_IN is specified, the described buffer will contain data read from the device on return from the HCD. Otherwise, the buffer contains driver-supplied data to be transferred to the device. The MDL must be allocated from nonpaged pool.


### -param transferBufferLength [in]

Specifies the length, in bytes, of the buffer specified in <i>TransferBuffer</i> or described in <i>TransferBufferMDL</i>.


### -param transferFlags [in]

Specifies zero, one, or a combination of the following flags:





#### USBD_TRANSFER_DIRECTION_IN

Is set to request data from a device. To transfer data to a device, this flag must be clear.



#### USBD_SHORT_TRANSFER_OK

Can be used if USBD_TRANSFER_DIRECTION_IN is set. If set, directs the HCD not to return an error if a packet is received from the device that is shorter than the maximum packet size for the endpoint. Otherwise, a short request returns an error condition.


### -param link [in]

Reserved. Must be set to <b>NULL</b>.


## -see-also

<a href="..\usb\ns-usb-_urb.md">URB</a>



<a href="..\usbspec\ns-usbspec-_usb_device_descriptor.md">USB_DEVICE_DESCRIPTOR</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540134">USB device driver programming reference</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20UsbBuildInterruptOrBulkTransferRequest routine%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

