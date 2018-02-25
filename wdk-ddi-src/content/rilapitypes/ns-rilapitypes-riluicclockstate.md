---
UID: NS:rilapitypes.RILUICCLOCKSTATE
title: RILUICCLOCKSTATE
author: windows-driver-content
description: This structure represents a RILUICCLOCKSTATE.
old-location: netvista\riluicclockstate.htm
old-project: netvista
ms.assetid: bc27f7b8-8de0-4eae-a22b-0e5c76378b1a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILUICCLOCKSTATE, ,, A, C, E, I, K, L, O, P, R, RILUICCLOCKSTATE, RILUICCLOCKSTATE structure [Network Drivers Starting with Windows Vista], S, T, U, netvista.riluicclockstate, rilapitypes/RILUICCLOCKSTATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILUICCLOCKSTATE
product: Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATE, *LPRILUICCLOCKSTATE
req.product: Windows 10 or later.
---

# RILUICCLOCKSTATE structure


## -description


<div class="alert"><b>Warning</b>  The Cellular COM API is deprecated in Windows 10. This content is provided to support maintenance of OEM and mobile operator created Windows Phone 8.1 applications.</div><div> </div>This structure represents a RILUICCLOCKSTATE.


## -syntax


````
struct RILUICCLOCKSTATE {
  DWORD       cbSize;
  DWORD       dwParams;
  RILUICCLOCK rilUiccLock;
  DWORD       dwLockState;
  DWORD       dwVerifyAttemptsLeft;
  DWORD       dwUnblockAttemptsLeft;
};
````


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



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [netvista\netvista]:%20RILUICCLOCKSTATE structure%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

