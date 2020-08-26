---
UID: NS:usbfnioctl._USBFN_POWER_FILTER_STATE
title: _USBFN_POWER_FILTER_STATE (usbfnioctl.h)
description: Reserved. Do not use.
old-location: buses\usbfn_power_filter_state.htm
tech.root: usbref
ms.assetid: D5C7DC47-37F7-4727-AFB6-137F67786001
ms.date: 05/07/2018
keywords: ["USBFN_POWER_FILTER_STATE structure"]
ms.keywords: "*PUSBFN_POWER_FILTER_STATE, PUSBFN_POWER_FILTER_STATE, PUSBFN_POWER_FILTER_STATE structure pointer [Buses], USBFN_POWER_FILTER_STATE, USBFN_POWER_FILTER_STATE structure [Buses], _USBFN_POWER_FILTER_STATE, buses.usbfn_power_filter_state, usbfnioctl/PUSBFN_POWER_FILTER_STATE, usbfnioctl/USBFN_POWER_FILTER_STATE"
f1_keywords:
 - "usbfnioctl/USBFN_POWER_FILTER_STATE"
 - "USBFN_POWER_FILTER_STATE"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- usbfnioctl.h
api_name:
- USBFN_POWER_FILTER_STATE
targetos: Windows
req.typenames: USBFN_POWER_FILTER_STATE, *PUSBFN_POWER_FILTER_STATE
---

# _USBFN_POWER_FILTER_STATE structure


## -description


Reserved. Do not use.


## -struct-fields




### -field DeviceState

Describes the USB device states for the device/controller.  These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.


### -field PState

USB device states for the device/controller.


### -field Reserved

Do not use. 


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_set_power_filter_exit_lpm">IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_EXIT_LPM</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/usbfnioctl/ni-usbfnioctl-ioctl_internal_usbfn_set_power_filter_state">IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE</a>
 

 

