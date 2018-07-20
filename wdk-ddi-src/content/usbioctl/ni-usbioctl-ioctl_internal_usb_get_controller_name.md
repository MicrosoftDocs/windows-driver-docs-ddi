---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME
title: IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME I/O request queries the bus driver for the device name of the USB host controller.
old-location: buses\ioctl_internal_usb_get_controller_name.htm
tech.root: usbref
ms.assetid: 52390982-febe-4d6d-b53a-160fb281b099
ms.author: windowsdriverdev
ms.date: 5/7/2018
ms.keywords: IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME, IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME control, IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME control code [Buses], buses.ioctl_internal_usb_get_controller_name, usbioctl/IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME, usbirp_36fbf149-8f7d-46ac-9ef3-017cbb000e1c.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: 
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
-	IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</b> I/O request queries the bus driver for the device name of the USB host controller. 

<b>IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.




## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> should be a pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540025">USB_HUB_NAME</a> structure that will be filled in with the name of the host controller.


### -input-buffer-length

<b>Parameters.Others.Argument2</b> should be a ULONG specifying the length of the buffer (in bytes) in <b>Parameters.Others.Argument1</b>.


### -output-buffer

The bus driver will fill the buffer pointed to by <b>Parameters.Others.Argument1</b> with the host controller device name. 


### -output-buffer-length

It will be filled only up to the length specified in <b>Parameters.Others.Argument2</b>.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The bus or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -remarks



The caller must supply a buffer that is large enough to hold a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540025">USB_HUB_NAME</a> structure. The  <b>Parameters.Others.Argument2</b> value indicates size of that buffer. Upon successful completion, the <b>HubName</b> member of <b>USB_HUB_NAME</b> contains the name of the controller and the <b>ActualLength</b> member indicates the length of the controller name string. Note that <b>ActualLength</b> does not indicate the size of the entire <b>USB_HUB_NAME</b> structure. If the buffer supplied in <b>Parameters.Others.Argument1</b> is not large enough to hold the string, the <b>HubName</b> value might show a truncated string.

To obtain the size of the buffer required to hold the string, send the request twice. In the first request, specify a buffer that is at least <code>sizeof(USB_HUB_NAME)</code> bytes. Otherwise, <b>ActualLength</b> does not indicate the correct length of the string and the request fails with STATUS_BUFFER_TOO_SMALL.

After the first request completes successfully, allocate a buffer of <code>ActualLength + sizeof(ULONG)</code> bytes and send the request again. After the request completes, <b>HubName</b> indicates the entire controller name string.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff540025">USB_HUB_NAME</a>
 

 

