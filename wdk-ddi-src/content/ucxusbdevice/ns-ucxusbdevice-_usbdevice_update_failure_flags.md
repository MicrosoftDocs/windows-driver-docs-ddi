---
UID: NS:ucxusbdevice._USBDEVICE_UPDATE_FAILURE_FLAGS
title: "_USBDEVICE_UPDATE_FAILURE_FLAGS"
author: windows-driver-content
description: The flags that are set by the client driver in the EVT_UCX_USBDEVICE_UPDATE callback function. Indicate errors, if any, that might have occurred while updating the device.
old-location: buses\_usbdevice_update_failure_flags.htm
old-project: usbref
ms.assetid: D01F8C2D-4E17-4FB7-A3C6-4B7EEDF07E0D
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, A, B, C, D, E, F, G, I, L, P, P_USBDEVICE_UPDATE_FAILURE_FLAGS, P_USBDEVICE_UPDATE_FAILURE_FLAGS structure pointer [Buses], R, S, T, U, USBDEVICE_UPDATE_FAILURE_FLAGS, USBDEVICE_UPDATE_FAILURE_FLAGS structure [Buses], V, _, _USBDEVICE_UPDATE_FAILURE_FLAGS, buses._usbdevice_update_failure_flags, ucxusbdevice/P_USBDEVICE_UPDATE_FAILURE_FLAGS, ucxusbdevice/_USBDEVICE_UPDATE_FAILURE_FLAGS"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ucxusbdevice.h
req.include-header: Ucxclass.h
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
-	ucxusbdevice.h
apiname:
-	USBDEVICE_UPDATE_FAILURE_FLAGS
product: Windows
targetos: Windows
req.typenames: USBDEVICE_UPDATE_FAILURE_FLAGS
req.product: Windows 10 or later.
---

# _USBDEVICE_UPDATE_FAILURE_FLAGS structure


## -description


The flags that are set by the client driver in the  <a href="..\ucxusbdevice\nc-ucxusbdevice-evt_ucx_usbdevice_update.md">EVT_UCX_USBDEVICE_UPDATE</a> callback function. Indicate errors, if any, that might have occurred while updating the device.


## -syntax


````
typedef struct _USBDEVICE_UPDATE_FAILURE_FLAGS {
  ULONG MaxExitLatencyTooLarge  :1;
  ULONG Reserved  :31;
} USBDEVICE_UPDATE_FAILURE_FLAGS, *P_USBDEVICE_UPDATE_FAILURE_FLAGS;
````


## -struct-fields




### -field MaxExitLatencyTooLarge

The maximum exit latency is larger than expected.


### -field Reserved

Do not use.


## -see-also

<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update.md">USBDEVICE_UPDATE</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_flags.md">USBDEVICE_UPDATE_FLAGS</a>



<a href="..\ucxusbdevice\ns-ucxusbdevice-_usbdevice_update_20_hardware_lpm_parameters.md">USBDEVICE_UPDATE_20_HARDWARE_LPM_PARAMETERS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [usbref\buses]:%20USBDEVICE_UPDATE_FAILURE_FLAGS structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

