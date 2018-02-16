---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME
title: IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME
author: windows-driver-content
description: The IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME I/O request queries the bus driver for the device name of the USB host controller.
old-location: buses\ioctl_internal_usb_get_controller_name.htm
old-project: usbref
ms.assetid: 52390982-febe-4d6d-b53a-160fb281b099
ms.author: windowsdriverdev
ms.date: 2/8/2018
ms.keywords: buses.ioctl_internal_usb_get_controller_name, IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME control code [Buses], IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME, usbioctl/IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME, usbirp_36fbf149-8f7d-46ac-9ef3-017cbb000e1c.xml
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	Usbioctl.h
apiname:
-	IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME
product: Windows
targetos: Windows
req.typenames: USB_HUB_TYPE
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description



The <b>IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</b> I/O request queries the bus driver for the device name of the USB host controller. 

<b>IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME</b> is a kernel-mode I/O control request. This request targets the USB hub PDO. This request must be sent at an IRQL of PASSIVE_LEVEL.




## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> should be a pointer to a <a href="..\usbioctl\ns-usbioctl-_usb_hub_name.md">USB_HUB_NAME</a> structure that will be filled in with the name of the host controller.


### -input-buffer-length

<b>Parameters.Others.Argument2</b> should be a ULONG specifying the length of the buffer (in bytes) in <b>Parameters.Others.Argument1</b>.


### -output-buffer

The bus driver will fill the buffer pointed to by <b>Parameters.Others.Argument1</b> with the host controller device name. 


### -output-buffer-length

It will be filled only up to the length specified in <b>Parameters.Others.Argument2</b>.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block

The bus or port driver sets <b>Irp-&gt;IoStatus.Status</b> to STATUS_SUCCESS or the appropriate error status.


## -remarks



The caller must supply a buffer that is large enough to hold a <a href="..\usbioctl\ns-usbioctl-_usb_hub_name.md">USB_HUB_NAME</a> structure. The  <b>Parameters.Others.Argument2</b> value indicates size of that buffer. Upon successful completion, the <b>HubName</b> member of <b>USB_HUB_NAME</b> contains the name of the controller and the <b>ActualLength</b> member indicates the length of the controller name string. Note that <b>ActualLength</b> does not indicate the size of the entire <b>USB_HUB_NAME</b> structure. If the buffer supplied in <b>Parameters.Others.Argument1</b> is not large enough to hold the string, the <b>HubName</b> value might show a truncated string.

To obtain the size of the buffer required to hold the string, send the request twice. In the first request, specify a buffer that is at least <code>sizeof(USB_HUB_NAME)</code> bytes. Otherwise, <b>ActualLength</b> does not indicate the correct length of the string and the request fails with STATUS_BUFFER_TOO_SMALL.

After the first request completes successfully, allocate a buffer of <code>ActualLength + sizeof(ULONG)</code> bytes and send the request again. After the request completes, <b>HubName</b> indicates the entire controller name string.




## -see-also

<a href="..\usbioctl\ns-usbioctl-_usb_hub_name.md">USB_HUB_NAME</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20IOCTL_INTERNAL_USB_GET_CONTROLLER_NAME control code%20 RELEASE:%20(2/8/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

