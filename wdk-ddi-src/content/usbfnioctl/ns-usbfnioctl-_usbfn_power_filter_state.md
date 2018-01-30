---
UID: NS:usbfnioctl._USBFN_POWER_FILTER_STATE
title: "_USBFN_POWER_FILTER_STATE"
author: windows-driver-content
description: Reserved. Do not use.
old-location: buses\usbfn_power_filter_state.htm
old-project: usbref
ms.assetid: D5C7DC47-37F7-4727-AFB6-137F67786001
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PUSBFN_POWER_FILTER_STATE structure pointer [Buses], USBFN_POWER_FILTER_STATE, PUSBFN_POWER_FILTER_STATE, _USBFN_POWER_FILTER_STATE, *PUSBFN_POWER_FILTER_STATE, buses.usbfn_power_filter_state, usbfnioctl/USBFN_POWER_FILTER_STATE, usbfnioctl/PUSBFN_POWER_FILTER_STATE, USBFN_POWER_FILTER_STATE structure [Buses]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	USBFN_POWER_FILTER_STATE
product: Windows
targetos: Windows
req.typenames: USBFN_POWER_FILTER_STATE, *PUSBFN_POWER_FILTER_STATE
req.product: Windows 10 or later.
---

# _USBFN_POWER_FILTER_STATE structure


## -description


Reserved. Do not use.


## -syntax


````
typedef struct _USBFN_POWER_FILTER_STATE {
  USBFN_DEVICE_STATE DeviceState;
  union {
    ULONG PState;
    ULONG Reserved;
  };
} USBFN_POWER_FILTER_STATE, *PUSBFN_POWER_FILTER_STATE;
````


## -struct-fields




### -field PState

USB device states for the device/controller.


### -field Reserved

Do not use. 


### -field DeviceState

Describes the USB device states for the device/controller.  These states correspond to the USB device states as defined in section 9.1 of the USB 2.0 Specification.


## -see-also

<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_set_power_filter_state.md">IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_STATE</a>

<a href="..\usbfnioctl\ni-usbfnioctl-ioctl_internal_usbfn_set_power_filter_exit_lpm.md">IOCTL_INTERNAL_USBFN_SET_POWER_FILTER_EXIT_LPM</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBFN_POWER_FILTER_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

