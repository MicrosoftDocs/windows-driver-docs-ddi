---
UID: NI:usbioctl.IOCTL_USB_HUB_CYCLE_PORT
title: IOCTL_USB_HUB_CYCLE_PORT
author: windows-driver-content
description: The IOCTL_USB_HUB_CYCLE_PORT I/O control request power-cycles the port that is associated with the PDO that receives the request.
old-location: buses\ioctl_usb_hub_cycle_port.htm
old-project: usbref
ms.assetid: 21d9af73-bd30-43d6-93b1-c29f763a4fcd
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_USB_HUB_CYCLE_PORT, IOCTL_USB_HUB_CYCLE_PORT control code [Buses], buses.ioctl_usb_hub_cycle_port, usbioctl/IOCTL_USB_HUB_CYCLE_PORT, usbirp_8e57d8e6-316b-475d-88cc-87e00b4ee6fb.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_USB_HUB_CYCLE_PORT
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_USB_HUB_CYCLE_PORT IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description



The <b>IOCTL_USB_HUB_CYCLE_PORT</b> I/O control request power-cycles the port that is associated with the PDO that receives the request. 

<b>IOCTL_USB_HUB_CYCLE_PORT</b> is a user-mode I/O control request. This request targets the USB hub device (GUID_DEVINTERFACE_USB_HUB).




## -ioctlparameters




### -input-buffer

The <b>AssociatedIrp.SystemBuffer</b> member points to a caller-allocated  <a href="..\usbioctl\ns-usbioctl-_usb_cycle_port_params.md">USB_CYCLE_PORT_PARAMS</a> structure that specifies the port number.


### -input-buffer-length

The size of a <a href="..\usbioctl\ns-usbioctl-_usb_cycle_port_params.md">USB_CYCLE_PORT_PARAMS</a> structure.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The USB stack sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS if the request is successful. Otherwise, the USB stack sets <b>Status</b> to the appropriate error condition, such as STATUS_INVALID_PARAMETER or STATUS_INSUFFICIENT_RESOURCES.


## -remarks



You can also power cycle the port by using the <b>Device Manager</b>'s <b>Enable</b>/<b>Disable</b> feature. This feature causes the bus driver to reset the device. Alternatively, you can use DevCon to enable or disable the device. 

The executable for DevCon can be found in the <i>&lt;install_path&gt;</i><b>\WinDDK\</b><i>build_number</i><b>\tools\devcon\</b><i>&lt;arch&gt;</i><b>\devcon.exe</b> folder.



