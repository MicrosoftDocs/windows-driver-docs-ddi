---
UID: NS:ntddrilapitypes.RILUICCLOCKSTATE
title: RILUICCLOCKSTATE (ntddrilapitypes.h)
description: This structure represents a RILUICCLOCKSTATE.
old-location: netvista\riluicclockstate.htm
tech.root: netvista
ms.date: 02/16/2018
keywords: ["RILUICCLOCKSTATE structure"]
ms.keywords: "*LPRILUICCLOCKSTATE, RILUICCLOCKSTATE, RILUICCLOCKSTATE structure [Network Drivers Starting with Windows Vista], netvista.riluicclockstate, rilapitypes/RILUICCLOCKSTATE"
req.header: ntddrilapitypes.h
req.include-header: Ntddrilapitypes.h
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
req.typenames: RILUICCLOCKSTATE, *LPRILUICCLOCKSTATE
f1_keywords:
 - RILUICCLOCKSTATE
 - ntddrilapitypes/RILUICCLOCKSTATE
 - LPRILUICCLOCKSTATE
 - ntddrilapitypes/LPRILUICCLOCKSTATE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - rilapitypes.h
api_name:
 - RILUICCLOCKSTATE
---

# RILUICCLOCKSTATE structure (ntddrilapitypes.h)


## -description

<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILUICCLOCKSTATE.

## -struct-fields

### -field cbSize

The size of the structure in bytes.

### -field dwParams

A bitwise combination of <a href="..\rilapitypes\ne-rilapitypes-riluicclockstateparammask.md">RILUICCLOCKSTATEPARAMMASK</a> enumeration values that indicates which members of the structure contain valid data. A member of the structure is valid if the corresponding bit flag is set.

### -field rilUiccLock

Specifies the lock of type <a href="..\rilapitypes\ns-rilapitypes-riluicclock.md">RILUICCLOCK</a>.

### -field dwLockState

The current state of the lock, a bitmask of <a href="..\rilapitypes\ne-rilapitypes-riluicclockstatelockstate.md">RILUICCLOCKSTATELOCKSTATE</a>.

### -field dwVerifyAttemptsLeft

The number of verification attempts that remain before the lock is blocked.

### -field dwUnblockAttemptsLeft

The number of unblock attempts that remain before the lock is permanently blocked.

## -syntax

```cpp
struct RILUICCLOCKSTATE {
  DWORD       cbSize;
  DWORD       dwParams;
  RILUICCLOCK rilUiccLock;
  DWORD       dwLockState;
  DWORD       dwVerifyAttemptsLeft;
  DWORD       dwUnblockAttemptsLeft;
};
```

## -see-also

<a href="/previous-versions/windows/hardware/cellular/dn946511(v=vs.85)">Cellular COM structures</a>
