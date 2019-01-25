---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION
title: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION (usbioctl.h)
description: The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION request retrieves information about the indicated USB port and the device that is attached to the port, if there is one.Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.
old-location: buses\ioctl_usb_get_node_connection_information.htm
tech.root: usbref
ms.assetid: abbd1f03-cf9e-449b-b261-2a751997fed0
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION control, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION control code [Buses], buses.ioctl_usb_get_node_connection_information, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_INFORMATION, usbirp_b71c24bb-6e3b-468f-851d-a934a764fbe1.xml
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
-	IOCTL_USB_GET_NODE_CONNECTION_INFORMATION
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_GET_NODE_CONNECTION_INFORMATION IOCTL


## -description



The <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</b> request retrieves information about the indicated USB port and the device that is attached to the port, if there is one.

Client drivers must send this IOCTL at an IRQL of PASSIVE_LEVEL.

<b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a user-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a> structure that describes the connection. On input, the <b>ConnectionIndex</b> member of this structure contains the port number.


### -input-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a> structure.


### -output-buffer

On output, the <b>Parameters.DeviceIoControl.OutputBufferLength</b> member contains the size of the output data. This size is variable, because it depends on the number of pipes that are associated with the port. 

<b>AssociatedIrp.SystemBuffer</b> points to a user-allocated <a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a> structure that contains the output data.


### -output-buffer-length

The size of a <a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a> structure.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The <a href="https://msdn.microsoft.com/library/windows/hardware/ff537321">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a> request is an extended version of <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</b>. The two requests are identical, except that the extended version of the request can report low, full, and high speed connections and the older <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION</b> request reports only low and full speed connections. For more information about the difference between these two requests, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a> and <a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff537321">IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540090">USB_NODE_CONNECTION_INFORMATION</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff540094">USB_NODE_CONNECTION_INFORMATION_EX</a>
 

 

