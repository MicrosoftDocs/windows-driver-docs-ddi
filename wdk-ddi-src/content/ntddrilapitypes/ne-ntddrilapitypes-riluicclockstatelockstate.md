---
UID: NE:ntddrilapitypes.RILUICCLOCKSTATELOCKSTATE
title: RILUICCLOCKSTATELOCKSTATE (ntddrilapitypes.h)
description: This enumeration describes the RILUICCLOCKSTATELOCKSTATE.
old-location: netvista\riluicclockstatelockstate.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILUICCLOCKSTATELOCKSTATE enumeration"]
ms.keywords: RILUICCLOCKSTATELOCKSTATE, RILUICCLOCKSTATELOCKSTATE enumeration [Network Drivers Starting with Windows Vista], RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, RIL_UICCLOCKSTATE_BLOCKED, RIL_UICCLOCKSTATE_ENABLED, RIL_UICCLOCKSTATE_VERIFIED, netvista.riluicclockstatelockstate, rilapitypes/RILUICCLOCKSTATELOCKSTATE, rilapitypes/RIL_PARAM_UICCLOCKSTATE_LOCKSTATE, rilapitypes/RIL_UICCLOCKSTATE_BLOCKED, rilapitypes/RIL_UICCLOCKSTATE_ENABLED, rilapitypes/RIL_UICCLOCKSTATE_VERIFIED
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
targetos: Windows
req.typenames: RILUICCLOCKSTATELOCKSTATE
f1_keywords:
 - RILUICCLOCKSTATELOCKSTATE
 - ntddrilapitypes/RILUICCLOCKSTATELOCKSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCLOCKSTATELOCKSTATE
---

# RILUICCLOCKSTATELOCKSTATE enumeration (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This enumeration describes the RILUICCLOCKSTATELOCKSTATE.

## -enum-fields

### -field RIL_UICCLOCKSTATE_NONE

### -field RIL_UICCLOCKSTATE_VERIFIED

Lock is verified.

### -field RIL_UICCLOCKSTATE_ENABLED

Lock is enabled.

### -field RIL_UICCLOCKSTATE_BLOCKED

Lock is blocked.

### -field RIL_UICCLOCKSTATE_ALL

### -field RIL_PARAM_UICCLOCKSTATE_LOCKSTATE

None of the other state bits are set.

## -syntax

```cpp
enum RILUICCLOCKSTATELOCKSTATE {
  RIL_PARAM_UICCLOCKSTATE_LOCKSTATE  = 0x0000000,
  RIL_UICCLOCKSTATE_VERIFIED         = 0x0000001,
  RIL_UICCLOCKSTATE_ENABLED          = 0x0000002,
  RIL_UICCLOCKSTATE_BLOCKED          = 0x0000003

};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946509(v=vs.85)">Cellular COM enumerations</a>
