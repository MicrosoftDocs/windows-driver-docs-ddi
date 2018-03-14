---
UID: NE:bthddi._BRB_VERSION
title: "_BRB_VERSION"
author: windows-driver-content
description: Reserved for internal use.
old-location: bltooth\brb_version.htm
old-project: bltooth
ms.assetid: 2bd4f3f6-94a4-47a6-8c15-a8f9bef5d2b5
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: BLUETOOTH_V1, BLUETOOTH_V2, BRB_VERSION, BRB_VERSION enumeration [Bluetooth Devices], _BRB_VERSION, bltooth.brb_version, bth_enums_d14431ac-24e9-4a27-90b9-a8aef7e38769.xml, bthddi/BLUETOOTH_V1, bthddi/BLUETOOTH_V2, bthddi/BRB_VERSION
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: bthddi.h
req.include-header: Bthddi.h
req.target-type: Windows
req.target-min-winverclnt: Versions:\_Supported in Windows Vista, and later.
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
req.irql: Developers should code this function to operate at either IRQL = DISPATCH_LEVEL (if the callback   function does not access paged memory), or IRQL = PASSIVE_LEVEL (if the callback function must access   paged memory)
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	bthddi.h
api_name:
-	BRB_VERSION
product: Windows
targetos: Windows
req.typenames: BRB_VERSION
---

# _BRB_VERSION enumeration


## -description


Reserved for internal use.


## -syntax


````
enum BRB_VERSION {
  BLUETOOTH_V1, 
  BLUETOOTH_V2 

};
````


## -enum-fields




### -field BLUETOOTH_V1

Reserved.


### -field BLUETOOTH_V2

Reserved.


## -see-also

<a href="..\bthddi\ns-bthddi-_brb.md">BRB</a>



<a href="..\bthddi\ns-bthddi-_brb_header.md">BRB_HEADER</a>



<a href="..\bthddi\nc-bthddi-pfnbth_allocate_brb.md">BthAllocateBrb</a>



<a href="..\bthioctl\ni-bthioctl-ioctl_internal_bth_submit_brb.md">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>



<a href="..\bthddi\nc-bthddi-pfnbth_initialize_brb.md">BthInitializeBrb</a>



 

 


