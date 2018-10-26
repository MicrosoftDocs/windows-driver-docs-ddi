---
UID: NE:ntddrilapitypes.RILUICCSLOTSTATE
title: RILUICCSLOTSTATE
author: windows-driver-content
description: This enumeration describes the RILUICCSLOTSTATE.
old-location: netvista\riluiccslotstate.htm
tech.root: netvista
ms.assetid: e88c6e79-c1a0-4ff9-ac00-f8f367aaa7c4
ms.date: 02/16/2018
ms.keywords: RILUICCSLOTSTATE, RILUICCSLOTSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_UICCSLOT_ACTIVE, RIL_UICCSLOT_EMPTY, RIL_UICCSLOT_ERROR, RIL_UICCSLOT_NOT_READY, RIL_UICCSLOT_OFF, RIL_UICCSLOT_OFF_EMPTY, netvista.riluiccslotstate, rilapitypes/RILUICCSLOTSTATE, rilapitypes/RIL_UICCSLOT_ACTIVE, rilapitypes/RIL_UICCSLOT_EMPTY, rilapitypes/RIL_UICCSLOT_ERROR, rilapitypes/RIL_UICCSLOT_NOT_READY, rilapitypes/RIL_UICCSLOT_OFF, rilapitypes/RIL_UICCSLOT_OFF_EMPTY
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
-	RILUICCSLOTSTATE
product:
- Windows
targetos: Windows
req.typenames: RILUICCSLOTSTATE
---

# RILUICCSLOTSTATE enumeration


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCSLOTSTATE.


## -syntax


```cpp
enum RILUICCSLOTSTATE {
  RIL_UICCSLOT_OFF_EMPTY  = 0x01,
  RIL_UICCSLOT_OFF        = 0x02,
  RIL_UICCSLOT_EMPTY      = 0x03,
  RIL_UICCSLOT_NOT_READY  = 0x04,
  RIL_UICCSLOT_ACTIVE     = 0x05,
  RIL_UICCSLOT_ERROR      = 0x06

};
```


## -enum-fields




### -field RIL_UICCSLOT_OFF_EMPTY


### -field RIL_UICCSLOT_OFF


### -field RIL_UICCSLOT_EMPTY


### -field RIL_UICCSLOT_NOT_READY


### -field RIL_UICCSLOT_ACTIVE


### -field RIL_UICCSLOT_ERROR


### -field RIL_UICCSLOT_MAX




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946509">Cellular COM enumerations</a>



 

 


