---
UID: NI:usbfnioctl.IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
title: IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
author: windows-driver-content
description: Do not use.
old-location: buses\ioctl_internal_usbfn_set_power_filter_state.htm
old-project: usbref
ms.assetid: 2C010516-500A-4CA2-B6FE-20333E7CCC39
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: buses.ioctl_internal_usbfn_set_power_filter_state, IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE control code [Buses], IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE, usbfnioctl/IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
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
-	IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE
product: Windows
targetos: Windows
req.typenames: USBFN_USB_STRING, *PUSBFN_USB_STRING
req.product: Windows 10 or later.
---

# IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE IOCTL


##  Major Code: 


[[XREF-LINK:IRP_MJ_DEVICE_CONTROL]

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


