---
UID: NS:rilapitypes.RILPERSODEACTIVATIONSTATE
title: RILPERSODEACTIVATIONSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilpersodeactivationstate_2.htm
old-project: netvista
ms.assetid: fb8950ef-7e46-45eb-b23f-5431488e1954
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILPERSODEACTIVATIONSTATE, netvista.rilpersodeactivationstate_2, rilapitypes/RILPERSODEACTIVATIONSTATE, RILPERSODEACTIVATIONSTATE, RILPERSODEACTIVATIONSTATE structure [Network Drivers Starting with Windows Vista]"
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rilapitypes.h
apiname:
-	RILPERSODEACTIVATIONSTATE
product: Windows
targetos: Windows
req.typenames: RILPERSODEACTIVATIONSTATE, *LPRILPERSODEACTIVATIONSTATE
req.product: Windows 10 or later.
---

# RILPERSODEACTIVATIONSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILPERSODEACTIVATIONSTATE {
  DWORD                                  cbSize;
  DWORD                                  dwParams;
  RILPERSODEACTIVATIONSTATEDEPERSOSTATE  dwDePersoState;
  DWORD                                  dwNumCKAttemptsLeft;
  DWORD                                  dwNumPUKAttemptsLeft;
} RILPERSODEACTIVATIONSTATE, RILPERSODEACTIVATIONSTATE;
````


## -struct-fields




#### - cbSize



#### - dwParams



#### - dwDePersoState



#### - dwNumCKAttemptsLeft



#### - dwNumPUKAttemptsLeft


