---
UID: NE:bthddi._ENUMERATOR_ACTION
title: "_ENUMERATOR_ACTION"
author: windows-driver-content
description: Reserved for internal use.
old-location: bltooth\enumerator_action.htm
old-project: bltooth
ms.assetid: d5acaec6-7b3b-4dd9-8901-f96b4e49149f
ms.author: windowsdriverdev
ms.date: 2/15/2018
ms.keywords: "*PENUMERATOR_ACTION, ENUMERATOR_ACTION, ENUMERATOR_ACTION enumeration [Bluetooth Devices], ENUMERATOR_ACTION enumeration pointer [Bluetooth Devices], ENUMERATOR_ACTION_CREATE, ENUMERATOR_ACTION_DESTROY, ENUMERATOR_ACTION_MAX, ENUMERATOR_ACTION_REMOVE, PENUMERATOR_ACTION, PENUMERATOR_ACTION enumeration pointer [Bluetooth Devices], _ENUMERATOR_ACTION, bltooth.enumerator_action, bth_enums_5ffc09cb-5aae-408c-ba92-b1872890541a.xml, bthddi/ENUMERATOR_ACTION, bthddi/ENUMERATOR_ACTION_CREATE, bthddi/ENUMERATOR_ACTION_DESTROY, bthddi/ENUMERATOR_ACTION_MAX, bthddi/ENUMERATOR_ACTION_REMOVE, bthddi/PENUMERATOR_ACTION"
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
-	ENUMERATOR_ACTION
product:
- Windows
targetos: Windows
req.typenames: ENUMERATOR_ACTION, *PENUMERATOR_ACTION
---

# _ENUMERATOR_ACTION enumeration


## -description


Reserved for internal use.


## -enum-fields




### -field ENUMERATOR_ACTION_CREATE

Reserved.


### -field ENUMERATOR_ACTION_REMOVE

Reserved.


### -field ENUMERATOR_ACTION_DESTROY

Reserved.


### -field ENUMERATOR_ACTION_MAX

Reserved.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff536607">BRB</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536612">BRB_HEADER</a>



<a href="https://msdn.microsoft.com/e1ac9d4c-75e2-4d37-86d7-3c3f1486222e">BthAllocateBrb</a>



<a href="https://msdn.microsoft.com/0b822d28-edaa-40cc-a678-112a356d9022">BthInitializeBrb</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff536751">IOCTL_INTERNAL_BTH_SUBMIT_BRB</a>
 

 

