---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_PORT_STATUS
title: IOCTL_INTERNAL_USB_GET_PORT_STATUS
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_PORT_STATUS I/O request queries the status of the PDO. IOCTL_INTERNAL_USB_GET_PORT_STATUS is a kernel-mode I/O control request. This request targets the USB hub PDO. This IOCTL must be sent at IRQL = PASSIVE_LEVEL.
old-location: buses\ioctl_internal_usb_get_port_status.htm
old-project: usbref
ms.assetid: eb15d01c-e77c-4605-9c12-dd8495834875
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_PORT_STATUS, IOCTL_INTERNAL_USB_GET_PORT_STATUS control, IOCTL_INTERNAL_USB_GET_PORT_STATUS control code [Buses], buses.ioctl_internal_usb_get_port_status, usbioctl/IOCTL_INTERNAL_USB_GET_PORT_STATUS, usbirp_4fc2e386-093d-45b3-a74d-da66e711d71d.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Usbioctl.h
api_name:
-	IOCTL_INTERNAL_USB_GET_PORT_STATUS
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_PORT_STATUS IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_GET_PORT_STATUS</b> I/O request queries the status of the PDO. 

<b>IOCTL_INTERNAL_USB_GET_PORT_STATUS</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This IOCTL must be sent at IRQL = PASSIVE_LEVEL.




## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> should be a pointer to a ULONG to be filled in with the port status flags.


### -input-buffer-length

The size of a ULONG.


### -output-buffer

<b>Parameters.Others.Argument1</b> points to a ULONG that has the port status flags filled in. The flags can be one or both of USBD_PORT_ENABLED (bit 0) or USBD_PORT_CONNECTED (bit 1). When the USB_PORT_ENABLED bit is set, the port has been enabled after resetting the device connected to the port. When the USB_PORT_ENABLED bit is clear, software has disabled the port or hardware has disabled it due to abnormal hardware conditions. When the USB_PORT_CONNECTED bit is set, the host controller root hub or external hub has detected that a device is connected to the port. When the USB_PORT_CONNECTED bit is clear, the host controller root hub or external hub has detected that a device is not connected to the port.


### -output-buffer-length

The size of a ULONG.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The bus or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.

