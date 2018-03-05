---
UID: NS:rilapitypes.RILUICCLOCKSTATE
title: RILUICCLOCKSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riluicclockstate_2.htm
old-project: netvista
ms.assetid: 18b933e6-cff3-49de-94ec-731a168c9d23
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILUICCLOCKSTATE, RILUICCLOCKSTATE, RILUICCLOCKSTATE structure [Network Drivers Starting with Windows Vista], netvista.riluicclockstate_2, rilapitypes/RILUICCLOCKSTATE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: rilapitypes.h
req.include-header: 
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
product: Windows
targetos: Windows
req.typenames: RILUICCLOCKSTATE, *LPRILUICCLOCKSTATE
req.product: Windows 10 or later.
---

# RILUICCLOCKSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILUICCLOCKSTATE {
  DWORD        cbSize;
  DWORD        dwParams;
  RILUICCLOCK  rilUiccLock;
  DWORD        dwLockState;
  DWORD        dwVerifyAttemptsLeft;
  DWORD        dwUnblockAttemptsLeft;
} RILUICCLOCKSTATE, RILUICCLOCKSTATE;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field rilUiccLock


### -field dwLockState


### -field dwVerifyAttemptsLeft


### -field dwUnblockAttemptsLeft

