---
UID: NE:ntddrilapitypes.RILNOTIFICATIONCLASSES
title: RILNOTIFICATIONCLASSES (ntddrilapitypes.h)
description: This enumeration describes the RILNOTIFICATIONCLASSES.
old-location: netvista\rilnotificationclasses.htm
tech.root: netvista
ms.assetid: f61fc609-40ca-40eb-a877-88c73cf3506e
ms.date: 02/16/2018
keywords: ["RILNOTIFICATIONCLASSES enumeration"]
ms.keywords: RILNOTIFICATIONCLASSES, RILNOTIFICATIONCLASSES enumeration [Network Drivers Starting with Windows Vista], RIL_NCLASS_FUNCRESULT, RIL_NCLASS_NOTIFICATIONS, netvista.rilnotificationclasses, rilapitypes/RILNOTIFICATIONCLASSES, rilapitypes/RIL_NCLASS_FUNCRESULT, rilapitypes/RIL_NCLASS_NOTIFICATIONS
f1_keywords:
 - "ntddrilapitypes/RILNOTIFICATIONCLASSES"
 - "RILNOTIFICATIONCLASSES"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- rilapitypes.h
api_name:
- RILNOTIFICATIONCLASSES
targetos: Windows
req.typenames: RILNOTIFICATIONCLASSES
---

# RILNOTIFICATIONCLASSES enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILNOTIFICATIONCLASSES.




## -syntax


```cpp
enum RILNOTIFICATIONCLASSES {
  RIL_NCLASS_FUNCRESULT     = 0x00000000,
  RIL_NCLASS_NOTIFICATIONS  = 0x10000000

};
```


## -enum-fields




### -field RIL_NCLASS_FUNCRESULT


### -field RIL_NCLASS_NOTIFICATIONS


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>



 

 


