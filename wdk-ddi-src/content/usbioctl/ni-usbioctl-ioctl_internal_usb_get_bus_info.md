---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_BUS_INFO
title: IOCTL_INTERNAL_USB_GET_BUS_INFO
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_BUS_INFO I/O request queries the bus driver for certain bus information.
old-location: buses\ioctl_internal_usb_get_bus_info.htm
old-project: usbref
ms.assetid: 31a5a829-1bb7-45cb-93b0-e899f7737df2
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_internal_usb_get_bus_info, IOCTL_INTERNAL_USB_GET_BUS_INFO control code [Buses], IOCTL_INTERNAL_USB_GET_BUS_INFO, usbioctl/IOCTL_INTERNAL_USB_GET_BUS_INFO, usbirp_6f2e2c9c-3bbc-40bd-a2e7-6fc79cfcc02b.xml
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
-	IOCTL_INTERNAL_USB_GET_BUS_INFO
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_BUS_INFO IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_INTERNAL_USB_GET_BUS_INFO</b> I/O request queries the bus driver for certain bus information. 

<b>IOCTL_INTERNAL_USB_GET_BUS_INFO</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.




## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> should be a pointer to a <b>USB_BUS_NOTIFICATION</b> structure.


### -input-buffer-length

The size of a <b>USB_BUS_NOTIFICATION</b> structure.


### -output-buffer

<b>Parameters.Others.Argument1</b> points to a <b>USB_BUS_NOTIFICATION</b> structure that has the <b>TotalBandwidth</b>, <b>ConsumedBandwidth</b>, and <b>ControllerNameLength</b> fields filled in.


### -output-buffer-length

The size of a <b>USB_BUS_NOTIFICATION</b> structure.


### -in-out-buffer


<text></text>



### -inout-buffer-length


<text></text>



### -status-block

The bus or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -see-also

<b>USB_BUS_NOTIFICATION</b>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USB_GET_BUS_INFO control code%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

