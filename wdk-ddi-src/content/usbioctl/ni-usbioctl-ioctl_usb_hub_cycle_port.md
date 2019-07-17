---
UID: NI:usbioctl.IOCTL_USB_HUB_CYCLE_PORT
title: IOCTL_USB_HUB_CYCLE_PORT (usbioctl.h)
description: The IOCTL_USB_HUB_CYCLE_PORT I/O control request power-cycles the port that is associated with the PDO that receives the request.
old-location: buses\ioctl_usb_hub_cycle_port.htm
tech.root: usbref
ms.assetid: 21d9af73-bd30-43d6-93b1-c29f763a4fcd
ms.date: 05/07/2018
ms.keywords: IOCTL_USB_HUB_CYCLE_PORT, IOCTL_USB_HUB_CYCLE_PORT control, IOCTL_USB_HUB_CYCLE_PORT control code [Buses], buses.ioctl_usb_hub_cycle_port, usbioctl/IOCTL_USB_HUB_CYCLE_PORT, usbirp_8e57d8e6-316b-475d-88cc-87e00b4ee6fb.xml
ms.topic: ioctl
f1_keywords:
 - "usbioctl/IOCTL_USB_HUB_CYCLE_PORT"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Supported on Windows 8 and later versions of Windows,  if the caller is running as Administrator. Supported on Microsoft Windows Server 2003, Windows XP-based versions of Windows. Not supported on Windows 7, Windows Vista, and Windows Server 2008.
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
- IOCTL_USB_HUB_CYCLE_PORT
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_USB_HUB_CYCLE_PORT IOCTL


## -description



The <b>IOCTL_USB_HUB_CYCLE_PORT</b> I/O control request power-cycles the port that is associated with the PDO that receives the request. 

<b>IOCTL_USB_HUB_CYCLE_PORT</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a caller-allocated  <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_cycle_port_params">USB_CYCLE_PORT_PARAMS</a> structure that specifies the port number.


### -input-buffer-length

The size of a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/usbioctl/ns-usbioctl-_usb_cycle_port_params">USB_CYCLE_PORT_PARAMS</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer








### -inout-buffer-length








### -status-block

The USB stack sets <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -remarks



You can also power cycle the port by using the <b>Device Manager</b>'s <b>Enable</b>/<b>Disable</b> feature. This feature causes the bus driver to reset the device. Alternatively, you can use DevCon to enable or disable the device. 

The executable for DevCon can be found in the <i><install_path></i><b>\WinDDK\</b><i>build_number</i><b>\tools\devcon\</b><i><arch></i><b>\devcon.exe</b> folder.



