---
UID: NI:usbioctl.IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2
title: IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2
author: windows-driver-content
description: The IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 I/O control is sent by an application to retrieve information about the protocols that are supported by a particular USB port on a hub. The request also retrieves the speed capability of the port.
old-location: buses\ioctl_usb_get_node_connection_information_ex_v2.htm
old-project: UsbRef
ms.assetid: 6B9BB412-EF3E-4115-87C7-1CB0CF557F7A
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.ioctl_usb_get_node_connection_information_ex_v2, IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 control code [Buses], IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2, usbioctl/IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: None supported
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
-	IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2 IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</b> I/O control is sent by an application to retrieve information about the protocols that are supported by a particular USB port on a hub. The request also retrieves the speed capability of the port.



<b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</b> is a user-mode I/O control request. This request targets the Universal Serial Bus (USB) hub device (GUID_DEVINTERFACE_USB_HUB). Do not send this request to the root hub.


## -ioctlparameters




### -input-buffer

<b>AssociatedIrp.SystemBuffer</b> points to a caller-allocated    <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2.md">USB_NODE_CONNECTION_INFORMATION_EX_V2</a> structure.

 On input, the caller must set the structure members as follows:<ul>
<li>
The caller must specify the port number in the <b>ConnectionIndex</b> member.  <b>ConnectionIndex</b> must be a value in the range of 1 to <i>n</i>, where <i>n</i> is the highest port number retrieved in a previous <a href="..\usbioctl\ni-usbioctl-ioctl_usb_get_hub_information_ex.md">IOCTL_USB_GET_HUB_INFORMATION_EX</a> I/O control request.

</li>
<li>
The caller must set a protocol flag in the <b>SupportedUsbProtocols</b> member (see <a href="..\usbioctl\ns-usbioctl-_usb_protocols.md">USB_PROTOCOLS</a>). In Windows 8, <b>SupportedUsbProtocols.Usb300</b> must be set to 1. Otherwise, the request fails with the STATUS_INVALID_PARAMETER error code.

</li>
<li>The caller must set the <b>Length</b> member to the size, in bytes, of the caller-allocated buffer pointed to by <b>AssociatedIrp.SystemBuffer</b>. The size of the buffer must be <code>sizeof (USB_NODE_CONNECTION_INFORMATION_EX_V2)</code>.</li>
</ul>



### -input-buffer-length

The <b>Parameters.DeviceIoControl.InputBufferLength</b> member indicates the size, in bytes, of the caller-allocated buffer whose size equals <code>sizeof(USB_NODE_CONNECTION_INFORMATION_EX_V2)</code>.


### -output-buffer

 On output, the <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2.md">USB_NODE_CONNECTION_INFORMATION_EX_V2</a> structure that is pointed to by  <b>AssociatedIrp.SystemBuffer</b> is filled with information about the attached device. 


### -output-buffer-length

The <b>Parameters.DeviceIoControl.OutputBufferLength</b> member indicates the size, in bytes, of the output buffer <b>SystemBuffer</b>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB driver stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -remarks



The <b>IOCTL_USB_GET_NODE_CONNECTION_INFORMATION_EX_V2</b> request queries the specified port's hub to get information about protocols supported by the port and the operating speed capability, if a device is attached to the port. 

If the request completes successfully, the <b>SupportedUsbProtocols.Usb200</b> member of <a href="..\usbioctl\ns-usbioctl-_usb_node_connection_information_ex_v2.md">USB_NODE_CONNECTION_INFORMATION_EX_V2</a> indicates protocols supported by the port. For instance, if the port supports signaling protocol defined by the USB 2.0 specification, then <b>SupportedUsbProtocols.Usb200</b> is set to 1.   

Note that  <b>SupportedUsbProtocols.Usb110</b> is always set to 1 for high-speed and full-speed hubs. That is because a high speed-capable hub  supports USB 1.1 protocol through split transactions and transaction translators. <b>SupportedUsbProtocols.Usb110</b> is never set to 1 for a USB 3.0 port. 

In addition, the request also determines whether the port and the attached device are capable of operating at SuperSpeed. If they are, the <b>Flags.DeviceIsSuperSpeedCapableOrHigher</b> member is set to 1. If the device attached to the port is currently operating  at SuperSpeed, then <b>DeviceIsOperatingAtSuperSpeedOrHigher</b> is set to 1.



