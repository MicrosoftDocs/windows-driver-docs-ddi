---
UID: NE:ntddrilapitypes.RILOPERATORNAMESPARAMMASK
title: RILOPERATORNAMESPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILOPERATORNAMESPARAMMASK.
old-location: netvista\riloperatornamesparammask.htm
tech.root: netvista
ms.assetid: f3e3654f-d317-4a8c-aa18-bbac86b06286
ms.date: 02/16/2018
ms.keywords: RILOPERATORNAMESPARAMMASK, RILOPERATORNAMESPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_ON_ALL, RIL_PARAM_ON_COUNTRY_CODE, RIL_PARAM_ON_LONGNAME, RIL_PARAM_ON_NUMNAME, RIL_PARAM_ON_SHORTNAME, RIL_PARAM_ON_SYSTEMTYPE, netvista.riloperatornamesparammask, rilapitypes/RILOPERATORNAMESPARAMMASK, rilapitypes/RIL_PARAM_ON_ALL, rilapitypes/RIL_PARAM_ON_COUNTRY_CODE, rilapitypes/RIL_PARAM_ON_LONGNAME, rilapitypes/RIL_PARAM_ON_NUMNAME, rilapitypes/RIL_PARAM_ON_SHORTNAME, rilapitypes/RIL_PARAM_ON_SYSTEMTYPE
f1_keywords:
 - "ntddrilapitypes/RILOPERATORNAMESPARAMMASK"
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
- RILOPERATORNAMESPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILOPERATORNAMESPARAMMASK
---

# RILOPERATORNAMESPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILOPERATORNAMESPARAMMASK.




## -syntax


```cpp
enum RILOPERATORNAMESPARAMMASK {
  RIL_PARAM_ON_LONGNAME      = 0x00000001,
  RIL_PARAM_ON_SHORTNAME     = 0x00000002,
  RIL_PARAM_ON_NUMNAME       = 0x00000004,
  RIL_PARAM_ON_COUNTRY_CODE  = 0x00000008,
  RIL_PARAM_ON_SYSTEMTYPE    = 0x00000010,
  RIL_PARAM_ON_ALL           = 0x0000001F

};
```


## -enum-fields




### -field RIL_PARAM_ON_LONGNAME


### -field RIL_PARAM_ON_SHORTNAME


### -field RIL_PARAM_ON_NUMNAME


### -field RIL_PARAM_ON_COUNTRY_CODE


### -field RIL_PARAM_ON_SYSTEMTYPE


### -field RIL_PARAM_ON_ALL


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>



 

 


