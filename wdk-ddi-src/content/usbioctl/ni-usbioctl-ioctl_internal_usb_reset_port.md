---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_RESET_PORT
title: IOCTL_INTERNAL_USB_RESET_PORT (usbioctl.h)
description: The IOCTL_INTERNAL_USB_RESET_PORT I/O control request is used by a driver to reset the upstream port of the device it manages.
old-location: buses\ioctl_internal_usb_reset_port.htm
tech.root: usbref
ms.assetid: 0ba0abfe-a32d-4650-ad08-f40d0b14f9a5
ms.date: 05/07/2018
ms.keywords: IOCTL_INTERNAL_USB_RESET_PORT, IOCTL_INTERNAL_USB_RESET_PORT control, IOCTL_INTERNAL_USB_RESET_PORT control code [Buses], buses.ioctl_internal_usb_reset_port, usbioctl/IOCTL_INTERNAL_USB_RESET_PORT, usbirp_d96d4c35-d399-444e-905b-c59360a01754.xml
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Usbioctl.h
api_name:
- IOCTL_INTERNAL_USB_RESET_PORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_RESET_PORT IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_RESET_PORT</b>  I/O control request is used by a driver to reset the upstream port of the device it manages. After a successful reset, the bus driver reselects the configuration and any alternative interface settings that the device had before the reset occurred. All pipe handles, configuration handles and interface handles remain valid.

Drivers should cancel all I/O requests and wait for them to complete before initiating this operation. 

A driver that manages an individual interface on a composite device cannot reset the interface without resetting the entire composite device and all of its interfaces. For this reason, drivers that manage interfaces should attempt other types of error recovery, such as resetting pipes (<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_pipe_request">_URB_PIPE_REQUEST</a>), before resetting the interface. 

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








### -inout-buffer-length








### -status-block

The bus or port driver sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usb/ns-usb-_urb_pipe_request">_URB_PIPE_REQUEST</a>
 

 

