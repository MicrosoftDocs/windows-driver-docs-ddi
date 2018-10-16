---
UID: NE:ntddrilapitypes.RILIMSSYSTEMTYPE
title: RILIMSSYSTEMTYPE
author: windows-driver-content
description: The RILIMSSYSTEMTYPE enumeration has the following values.
old-location: netvista\rilimssystemtype.htm
tech.root: netvista
ms.assetid: e1f5dde2-8e45-4904-bbf3-bd2358f95a5b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RILIMSSYSTEMTYPE, RILIMSSYSTEMTYPE enumeration [Network Drivers Starting with Windows Vista], RIL_IMSSYSTEMTYPE_LTE, RIL_IMSSYSTEMTYPE_MAX, RIL_IMSSYSTEMTYPE_UNKNOWN, RIL_IMSSYSTEMTYPE_WIFI, netvista.rilimssystemtype, rilapitypes/RILIMSSYSTEMTYPE, rilapitypes/RIL_IMSSYSTEMTYPE_LTE, rilapitypes/RIL_IMSSYSTEMTYPE_MAX, rilapitypes/RIL_IMSSYSTEMTYPE_UNKNOWN, rilapitypes/RIL_IMSSYSTEMTYPE_WIFI
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h, Ntddrilapitypes.h
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
-	rilapitypes.h
api_name:
-	RILIMSSYSTEMTYPE
product:
- Windows
targetos: Windows
req.typenames: RILIMSSYSTEMTYPE
---

# RILIMSSYSTEMTYPE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>The RILIMSSYSTEMTYPE enumeration has the following values.




## -syntax


```cpp
enum RILIMSSYSTEMTYPE {
  RIL_IMSSYSTEMTYPE_UNKNOWN  = 0x00000000,
  RIL_IMSSYSTEMTYPE_WIFI     = 0x00000001,
  RIL_IMSSYSTEMTYPE_LTE      = 0x00000002,
  RIL_IMSSYSTEMTYPE_MAX      = RIL_IMSSYSTEMTYPE_LTE

};
```


## -enum-fields




### -field RIL_IMSSYSTEMTYPE_UNKNOWN


### -field RIL_IMSSYSTEMTYPE_WIFI


### -field RIL_IMSSYSTEMTYPE_LTE


### -field RIL_IMSSYSTEMTYPE_MAX


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


