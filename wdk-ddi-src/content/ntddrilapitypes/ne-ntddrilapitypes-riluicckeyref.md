---
UID: NE:ntddrilapitypes.RILUICCKEYREF
title: RILUICCKEYREF
description: This enumeration describes the RILUICCAPPTYPE.
old-location: netvista\riluicckeyref.htm
tech.root: netvista
ms.assetid: 7812008b-867f-4b17-b715-7a1f10c38368
ms.date: 02/16/2018
ms.keywords: RILUICCKEYREF, RILUICCKEYREF enumeration [Network Drivers Starting with Windows Vista], RIL_UICCKEYREF_ALW, RIL_UICCKEYREF_NEV, RIL_UICCKEYREF_PIN1, RIL_UICCKEYREF_PIN2, RIL_UICCKEYREF_UPIN, netvista.riluicckeyref, rilapitypes/RILUICCKEYREF, rilapitypes/RIL_UICCKEYREF_ALW, rilapitypes/RIL_UICCKEYREF_NEV, rilapitypes/RIL_UICCKEYREF_PIN1, rilapitypes/RIL_UICCKEYREF_PIN2, rilapitypes/RIL_UICCKEYREF_UPIN
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
-	RILUICCKEYREF
product:
- Windows
targetos: Windows
req.typenames: RILUICCKEYREF
---

# RILUICCKEYREF enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCAPPTYPE.


## -syntax


```cpp
enum RILUICCKEYREF {
  RIL_UICCKEYREF_ALW   = 0x00,
  RIL_UICCKEYREF_PIN1  = 0x01,
  RIL_UICCKEYREF_UPIN  = 0x10,
  RIL_UICCKEYREF_PIN2  = 0x81,
  RIL_UICCKEYREF_NEV   = 0xff

};
```


## -enum-fields




### -field RIL_UICCKEYREF_ALW


### -field RIL_UICCKEYREF_PIN1


### -field RIL_UICCKEYREF_UPIN


### -field RIL_UICCKEYREF_PIN2


### -field RIL_UICCKEYREF_NEV


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


