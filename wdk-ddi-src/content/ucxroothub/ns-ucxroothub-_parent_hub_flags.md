---
UID: NS:ucxroothub._PARENT_HUB_FLAGS
title: "_PARENT_HUB_FLAGS" (ucxroothub.h)
description: This structure is used by the HUB_INFO_FROM_PARENT structure to get hub information from the parent.
old-location: buses\_parent_hub_flags.htm
tech.root: usbref
ms.assetid: 9107CC24-48FF-4A2C-AA27-1E9E316B7944
ms.date: 05/07/2018
ms.keywords: "*PPARENT_HUB_FLAGS, PARENT_HUB_FLAGS, PARENT_HUB_FLAGS union [Buses], _PARENT_HUB_FLAGS, buses._parent_hub_flags, ucxroothub/_PARENT_HUB_FLAGS"
ms.topic: struct
req.header: ucxroothub.h
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ucxroothub.h
api_name:
-	PARENT_HUB_FLAGS
product:
- Windows
targetos: Windows
req.typenames: PARENT_HUB_FLAGS, *PPARENT_HUB_FLAGS
---

# _PARENT_HUB_FLAGS structure


## -description


This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt188022">HUB_INFO_FROM_PARENT</a> structure to get hub information from the parent.


## -struct-fields




### -field AsUlong32

The size of structure represented as a LONG (32-bit) value.


### -field Flags

 


### -field Flags.DisableLpmForAllDownstreamDevices
Indicates that LPM should be disabled for all devices/hubs behind the this hub.
 

### -field Flags.HubIsHighSpeedCapable
Indicates that the hub is high-speed capable.

### -field Flags.DisableUpdateMaxExitLatency
Indicates that UpdateMaxExitLatency is disabled for all devices/hubs behind the this hub. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt188022">HUB_INFO_FROM_PARENT</a>
 

 

