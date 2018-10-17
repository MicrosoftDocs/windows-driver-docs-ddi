---
UID: NE:ntddrilapitypes.RILADDRESSNUMPLAN
title: RILADDRESSNUMPLAN
author: windows-driver-content
description: This enumeration describes the RILADDRESSNUMPLAN.
old-location: netvista\riladdressnumplan.htm
tech.root: netvista
ms.assetid: fa25ce95-3eed-41f3-a0eb-5c290fa032e8
ms.date: 2/16/2018
ms.keywords: RILADDRESSNUMPLAN, RILADDRESSNUMPLAN enumeration [Network Drivers Starting with Windows Vista], RIL_NUMPLAN_DATA, RIL_NUMPLAN_ERMES, RIL_NUMPLAN_NATIONAL, RIL_NUMPLAN_PRIVATE, RIL_NUMPLAN_TELEPHONE, RIL_NUMPLAN_TELEX, RIL_NUMPLAN_UNKNOWN, netvista.riladdressnumplan, rilapitypes/RILADDRESSNUMPLAN, rilapitypes/RIL_NUMPLAN_DATA, rilapitypes/RIL_NUMPLAN_ERMES, rilapitypes/RIL_NUMPLAN_NATIONAL, rilapitypes/RIL_NUMPLAN_PRIVATE, rilapitypes/RIL_NUMPLAN_TELEPHONE, rilapitypes/RIL_NUMPLAN_TELEX, rilapitypes/RIL_NUMPLAN_UNKNOWN
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
-	RILADDRESSNUMPLAN
product:
- Windows
targetos: Windows
req.typenames: RILADDRESSNUMPLAN
---

# RILADDRESSNUMPLAN enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILADDRESSNUMPLAN.




## -syntax


```
enum RILADDRESSNUMPLAN {
  RIL_NUMPLAN_UNKNOWN    = 0x00000000,
  RIL_NUMPLAN_TELEPHONE  = 0x00000001,
  RIL_NUMPLAN_DATA       = 0x00000002,
  RIL_NUMPLAN_TELEX      = 0x00000003,
  RIL_NUMPLAN_NATIONAL   = 0x00000004,
  RIL_NUMPLAN_PRIVATE    = 0x00000005,
  RIL_NUMPLAN_ERMES      = 0x00000006

};
```


## -enum-fields




### -field RIL_NUMPLAN_UNKNOWN


### -field RIL_NUMPLAN_TELEPHONE


### -field RIL_NUMPLAN_DATA


### -field RIL_NUMPLAN_TELEX


### -field RIL_NUMPLAN_NATIONAL


### -field RIL_NUMPLAN_PRIVATE


### -field RIL_NUMPLAN_ERMES


### -field RIL_NUMPLAN_MAX




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


