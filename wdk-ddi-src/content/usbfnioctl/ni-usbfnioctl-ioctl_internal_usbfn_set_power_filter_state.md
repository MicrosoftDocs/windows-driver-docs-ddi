---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
title: IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
author: windows-driver-content
description: Do not use.
old-location: buses\ioctl_internal_usbfn_set_power_filter_state.htm
old-project: usbref
ms.assetid: 2C010516-500A-4CA2-B6FE-20333E7CCC39
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE, IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE control code [Buses], buses.ioctl_internal_usbfn_set_power_filter_state, usbfnioctl/IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	usbfnioctl.h
api_name:
-	IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE IOCTL


##  Major Code: 


[IRP_MJ_DEVICE_CONTROL](https://docs.microsoft.com/en-us/windows-hardware/drivers/kernel/irp-mj-device-control)

## -description


Do not use.
		ucxc
   	


## -ioctlparameters




### -input-buffer

The input buffer contains a <a href="..\usbfnioctl\ns-usbfnioctl-_usbfn_power_filter_state.md">USBFN_POWER_FILTER_STATE</a> structure that specifies the device state.


### -input-buffer-length

The size of a <a href="..\usbfnioctl\ns-usbfnioctl-_usbfn_power_filter_state.md">USBFN_POWER_FILTER_STATE</a> structure.


### -output-buffer

NULL.


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



