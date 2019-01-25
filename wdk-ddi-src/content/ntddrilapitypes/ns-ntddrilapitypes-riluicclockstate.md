---
UID: NS:ntddrilapitypes.RILUICCLOCKSTATE
title: RILUICCLOCKSTATE (ntddrilapitypes.h)
description: This structure represents a RILUICCLOCKSTATE.
old-location: netvista\riluicclockstate.htm
tech.root: netvista
ms.assetid: bc27f7b8-8de0-4eae-a22b-0e5c76378b1a
ms.date: 02/16/2018
ms.keywords: "*LPRILUICCLOCKSTATE, RILUICCLOCKSTATE, RILUICCLOCKSTATE structure [Network Drivers Starting with Windows Vista], netvista.riluicclockstate, rilapitypes/RILUICCLOCKSTATE"
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	rilapitypes.h
api_name:
-	RILUICCLOCKSTATE
product:
- Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATE, *LPRILUICCLOCKSTATE
---

# RILUICCLOCKSTATE structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILUICCLOCKSTATE.


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


## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/dn946511">Cellular COM structures</a>



 

 


