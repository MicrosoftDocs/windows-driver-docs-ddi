---
UID: NI:usbioctl.IOCTL_INTERNAL_USB_SUBMIT_URB
title: IOCTL_INTERNAL_USB_SUBMIT_URB (usbioctl.h)
description: The IOCTL_INTERNAL_USB_SUBMIT_URB I/O control request is used by drivers to submit an URB to the bus driver. IOCTL_INTERNAL_USB_SUBMIT_URB is a kernel-mode I/O control request. This request targets the USB hub PDO.
old-location: buses\ioctl_internal_usb_submit_urb.htm
tech.root: usbref
ms.assetid: ea4e1550-7972-4fc8-ac65-e6b4bba82f15
ms.date: 05/07/2018
keywords: ["IOCTL_INTERNAL_USB_SUBMIT_URB IOCTL"]
ms.keywords: IOCTL_INTERNAL_USB_SUBMIT_URB, IOCTL_INTERNAL_USB_SUBMIT_URB control, IOCTL_INTERNAL_USB_SUBMIT_URB control code [Buses], buses.ioctl_internal_usb_submit_urb, usbioctl/IOCTL_INTERNAL_USB_SUBMIT_URB, usbirp_2df110d3-a22d-4074-b14f-125afd943afa.xml
f1_keywords:
 - "usbioctl/IOCTL_INTERNAL_USB_SUBMIT_URB"
 - "IOCTL_INTERNAL_USB_SUBMIT_URB"
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
- IOCTL_INTERNAL_USB_SUBMIT_URB
product:
- Windows
targetos: Windows
req.typenames: 
---

# IOCTL_INTERNAL_USB_SUBMIT_URB IOCTL


## -description



The <b>IOCTL_INTERNAL_USB_SUBMIT_URB</b> I/O control request is used by drivers to submit an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> to the bus driver. 

<b>IOCTL_INTERNAL_USB_SUBMIT_URB</b> is a kernel-mode I/O control request. This request targets the USB hub PDO.




## -ioctlparameters




### -input-buffer

<b>Parameters.Others.Argument1</b> points to the URB, a variable-length structure. The <b>UrbHeader.Function</b> member of the URB specifies the URB type. The length of URB, as well as the meaning of any additional members depends on the value of <b>UrbHeader.Function</b>. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> for details.


### -input-buffer-length

The <b>UrbHeader.Length</b> member specifies the size in bytes of the URB. 


### -output-buffer

<b>Parameters.Others.Argument1</b> points to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a> structure. The <b>UrbHeader.Status</b> contains a USB status code for the requested operation. Any additional output depends on the <b>UrbHeader.Function</b> member of the URB submitted. See <b>URB</b> for details.


### -output-buffer-length

The <b>UrbHeader.Length</b> member specifies the size in bytes of the URB. 


### -in-out-buffer








### -inout-buffer-length








### -status-block

The lower-level drivers will set <b>Irp->IoStatus.Status</b> to STATUS_SUCCESS if the URB can be successfully processed. Otherwise, the bus driver will set it to the appropriate error condition, such as STATUS_INVALID_PARAMETER, or STATUS_INSUFFICIENT_RESOURCES.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usb/ns-usb-_urb">URB</a>
 

 

