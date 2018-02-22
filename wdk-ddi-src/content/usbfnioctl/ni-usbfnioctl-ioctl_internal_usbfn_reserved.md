---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_RESERVED
title: IOCTL_INTERNAL_USBFN_RESERVED
author: windows-driver-content
description: Do not use.
old-location: buses\ioctl_internal_usbfn_reserved.htm
old-project: UsbRef
ms.assetid: F6935F5F-B6A8-4495-835D-151A26633F04
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: buses.ioctl_internal_usbfn_reserved, IOCTL_INTERNAL_USBFN_RESERVED control code [Buses], IOCTL_INTERNAL_USBFN_RESERVED, usbfnioctl/IOCTL_INTERNAL_USBFN_RESERVED
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: ioctl
req.header: usbfnioctl.h
req.include-header: Usbfnioctl.h
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
-	usbfnioctl.h
apiname:
-	IOCTL_INTERNAL_USBFN_RESERVED
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_RESERVED IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

## -description


Do not use.


## -ioctlparameters




### -input-buffer

None.


### -input-buffer-length

None.


### -output-buffer

None.


### -output-buffer-length

None.


### -in-out-buffer



<text></text>




### -inout-buffer-length



<text></text>




### -status-block



Irp->IoStatus.Status is set to STATUS_SUCCESS if the request is successful.

Otherwise, Status to the appropriate error condition as a NTSTATUS code. 

For more information, see [XREF-LINK:NTSTATUS Values].



