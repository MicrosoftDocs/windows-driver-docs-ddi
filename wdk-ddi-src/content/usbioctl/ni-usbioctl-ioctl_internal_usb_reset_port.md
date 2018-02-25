---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_RESET_PORT
title: IOCTL_INTERNAL_USB_RESET_PORT
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_RESET_PORT I/O control request is used by a driver to reset the upstream port of the device it manages.
old-location: buses\ioctl_internal_usb_reset_port.htm
old-project: UsbRef
ms.assetid: 0ba0abfe-a32d-4650-ad08-f40d0b14f9a5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: IOCTL_INTERNAL_USB_RESET_PORT, IOCTL_INTERNAL_USB_RESET_PORT control code [Buses], buses.ioctl_internal_usb_reset_port, usbioctl/IOCTL_INTERNAL_USB_RESET_PORT, usbirp_d96d4c35-d399-444e-905b-c59360a01754.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_RESET_PORT
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_RESET_PORT IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The <b>IOCTL_INTERNAL_USB_RESET_PORT</b>  I/O control request is used by a driver to reset the upstream port of the device it manages. After a successful reset, the bus driver reselects the configuration and any alternative interface settings that the device had before the reset occurred. All pipe handles, configuration handles and interface handles remain valid.

Drivers should cancel all I/O requests and wait for them to complete before initiating this operation. 

A driver that manages an individual interface on a composite device cannot reset the interface without resetting the entire composite device and all of its interfaces. For this reason, drivers that manage interfaces should attempt other types of error recovery, such as resetting pipes (<a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a>), before resetting the interface. 

This IOCTL must be sent at an IRQL of PASSIVE_LEVEL.

<b>IOCTL_INTERNAL_USB_RESET_PORT</b> is a kernel-mode I/O control request. This request targets the USB hub PDO.




## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The bus or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -see-also

<a href="..\usb\ns-usb-_urb_pipe_request.md">_URB_PIPE_REQUEST</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20IOCTL_INTERNAL_USB_RESET_PORT control code%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

