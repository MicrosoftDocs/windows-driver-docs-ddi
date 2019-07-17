---
UID: NE:ntddrilapitypes.RILUICCLOCKSTATEPARAMMASK
title: RILUICCLOCKSTATEPARAMMASK (ntddrilapitypes.h)
description: This enumeration describes the RILUICCLOCKSTATEPARAMMASK.
old-location: netvista\riluicclockstateparammask.htm
tech.root: netvista
ms.assetid: 19366fbe-8a04-4a9f-9acc-8de0211e6e0d
ms.date: 02/16/2018
ms.keywords: RILUICCLOCKSTATEPARAMMASK, RILUICCLOCKSTATEPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UICCLOCKSTATE_ALL, RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, RIL_PARAM_UICCLOCKSTATE_UICCLOCK, RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT, RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT, netvista.riluicclockstateparammask, rilapitypes/RILUICCLOCKSTATEPARAMMASK, rilapitypes/RIL_PARAM_UICCLOCKSTATE_ALL, rilapitypes/RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, rilapitypes/RIL_PARAM_UICCLOCKSTATE_UICCLOCK, rilapitypes/RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT, rilapitypes/RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT
ms.topic: enum
f1_keywords:
 - "ntddrilapitypes/RILUICCLOCKSTATEPARAMMASK"
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
- RILUICCLOCKSTATEPARAMMASK
product:
- Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATEPARAMMASK
---

# RILUICCLOCKSTATEPARAMMASK enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCLOCKSTATEPARAMMASK.


## -syntax


```cpp
enum RILUICCLOCKSTATEPARAMMASK {
  RIL_PARAM_UICCLOCKSTATE_UICCLOCK             = 0x00000001,
  RIL_PARAM_UICCLOCKSTATE_LOCKSTATE            = 0x00000002,
  RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT   = 0x00000004,
  RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT  = 0x00000008,
  RIL_PARAM_UICCLOCKSTATE_ALL                  = 0x0000000F

};
```


## -enum-fields




### -field RIL_PARAM_UICCLOCKSTATE_UICCLOCK


### -field RIL_PARAM_UICCLOCKSTATE_LOCKSTATE


### -field RIL_PARAM_UICCLOCKSTATE_VERIFYATTEMPTSLEFT


### -field RIL_PARAM_UICCLOCKSTATE_UNBLOCKATTEMPTSLEFT


### -field RIL_PARAM_UICCLOCKSTATE_ALL


## -see-also

<a href="https://docs.microsoft.com/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>



 

 


