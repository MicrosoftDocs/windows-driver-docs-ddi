---
UID: NS:ucxroothub._PARENT_HUB_FLAGS
title: "_PARENT_HUB_FLAGS"
author: windows-driver-content
description: This structure is used by the HUB_INFO_FROM_PARENT structure to get hub information from the parent.
old-location: buses\_parent_hub_flags.htm
old-project: UsbRef
ms.assetid: 9107CC24-48FF-4A2C-AA27-1E9E316B7944
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "_PARENT_HUB_FLAGS, ucxroothub/_PARENT_HUB_FLAGS, buses._parent_hub_flags, *PPARENT_HUB_FLAGS, PARENT_HUB_FLAGS, PARENT_HUB_FLAGS union [Buses]"
ms.prod: windows-hardware
ms.technology: windows-devices
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
req.irql: "<=DISPATCH_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	ucxroothub.h
apiname:
-	PARENT_HUB_FLAGS
product: Windows
targetos: Windows
req.typenames: PARENT_HUB_FLAGS, *PPARENT_HUB_FLAGS
req.product: Windows 10 or later.
---

# _PARENT_HUB_FLAGS structure


## -description


This structure is used by the <a href="..\ucxroothub\ns-ucxroothub-_hub_info_from_parent.md">HUB_INFO_FROM_PARENT</a> structure to get hub information from the parent.


## -syntax


````
typedef union _PARENT_HUB_FLAGS {
  ULONG  AsUlong32;
  struct {
    ULONG DisableLpmForAllDownstreamDevices  :1;
    ULONG HubIsHighSpeedCapable  :1;
  };
} PARENT_HUB_FLAGS;
````


## -struct-fields




### -field AsUlong32

The size of structure represented as a LONG (32-bit) value.


### -field Flags

 




#### - DisableLpmForAllDownstreamDevices

Indicates that all devices behind the hub must be disabled.


#### - HubIsHighSpeedCapable

Indicates that the hub is high-speed capable.


## -see-also

<a href="..\ucxroothub\ns-ucxroothub-_hub_info_from_parent.md">HUB_INFO_FROM_PARENT</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [UsbRef\buses]:%20PARENT_HUB_FLAGS union%20 RELEASE:%20(2/15/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

