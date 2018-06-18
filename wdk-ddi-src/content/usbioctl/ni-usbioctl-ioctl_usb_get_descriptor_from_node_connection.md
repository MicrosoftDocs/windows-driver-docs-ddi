---
UID: NI:usbioctl.IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
title: IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
author: windows-driver-content
description: The IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION is a user-mode I/O control request.
old-location: buses\ioctl_usb_get_descriptor_from_node_connection.htm
old-project: usbref
ms.assetid: 60b41f73-ef12-4d3f-9df4-8958ab66bf14
ms.author: windowsdriverdev
ms.date: 4/25/2018
ms.keywords: IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION, IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION control, IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION control code [Buses], buses.ioctl_usb_get_descriptor_from_node_connection, usbioctl/IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION, usbirp_060f6333-3fe9-4a4b-8ff1-f7403a3e8dfe.xml
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
-	IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION IOCTL


## -description



The <b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> I/O control request retrieves one or more descriptors for the device that is associated with the indicated port index.

<b>IOCTL_USB_GET_DESCRIPTOR_FROM_NODE_CONNECTION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a <a href="https://msdn.microsoft.com/library/windows/hardware/ff539272">USB_DESCRIPTOR_REQUEST</a> structure that describes the descriptor request. 


### -input-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the user-allocated output buffer in the <b>Data</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539272">USB_DESCRIPTOR_REQUEST</a> structure. 


### -output-buffer

The <b>Data</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff539272">USB_DESCRIPTOR_REQUEST</a> structure at <b>AssociatedIrp.SystemBuffer</b> points to the output buffer.


### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff539272">USB_DESCRIPTOR_REQUEST</a>
 

 

