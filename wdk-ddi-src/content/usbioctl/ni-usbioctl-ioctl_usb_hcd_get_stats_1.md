---
UID: NI:usbioctl.IOCTL_USB_HCD_GET_STATS_1
title: IOCTL_USB_HCD_GET_STATS_1 (usbioctl.h)
description: The IOCTL_USB_HCD_GET_STATS_1 IOCTL has been deprecated. Do not use.
old-location: buses\ioctl_usb_hcd_get_stats_1.htm
tech.root: usbref
ms.assetid: 8be34d4d-b2f1-4d34-911a-95ac2e19df87
ms.date: 05/07/2018
keywords: ["IOCTL_USB_HCD_GET_STATS_1 IOCTL"]
ms.keywords: IOCTL_USB_HCD_GET_STATS_1, IOCTL_USB_HCD_GET_STATS_1 control, IOCTL_USB_HCD_GET_STATS_1 control code [Buses], buses.ioctl_usb_hcd_get_stats_1, usbioctl/IOCTL_USB_HCD_GET_STATS_1, usbirp_2817a2bf-23af-43f8-8c50-c945cf2544f0.xml
f1_keywords:
 - "usbioctl/IOCTL_USB_HCD_GET_STATS_1"
 - "IOCTL_USB_HCD_GET_STATS_1"
req.header: usbioctl.h
req.include-header: Usbioctl.h
req.target-type: Windows
req.target-min-winverclnt: Available on Microsoft Windows Server 2003, Windows XP, and Windows 2000, but it is not available on Windows Vista.
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
- IOCTL_USB_HCD_GET_STATS_1
targetos: Windows
req.typenames: 
---

# IOCTL_USB_HCD_GET_STATS_1 IOCTL


## -description


The <b>IOCTL_USB_HCD_GET_STATS_1</b> IOCTL has been deprecated. Do not use.


## -ioctlparameters




### -input-buffer








### -input-buffer-length








### -output-buffer








### -output-buffer-length








### -in-out-buffer








### -inout-buffer-length








### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [NTSTATUS Values](https://docs.microsoft.com/windows-hardware/drivers/kernel/ntstatus-values).



