---
UID: NE:rilapitypes.RILCALLMEDIAVIDEOFLAGPARAMMASK
title: RILCALLMEDIAVIDEOFLAGPARAMMASK
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediavideoflagparammask_2.htm
old-project: netvista
ms.assetid: 6f0a8c1f-e3cb-4bcb-a9ec-4d4b7555a314
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RIL_CALLMEDIAVIDEOFLAG_ALL, RILCALLMEDIAVIDEOFLAGPARAMMASK enumeration [Network Drivers Starting with Windows Vista], RIL_CALLMEDIAVIDEOFLAG_CAPABILITY_UNKNOWN, rilapitypes/RIL_CALLMEDIAVIDEOFLAG_PAUSE, rilapitypes/RILCALLMEDIAVIDEOFLAGPARAMMASK, RILCALLMEDIAVIDEOFLAGPARAMMASK, RIL_CALLMEDIAVIDEOFLAG_PAUSE, rilapitypes/RIL_CALLMEDIAVIDEOFLAG_TEMPORARILY_UNAVAILABLE, rilapitypes/RIL_CALLMEDIAVIDEOFLAG_CAPABILITY_UNKNOWN, rilapitypes/RIL_CALLMEDIAVIDEOFLAG_ALL, netvista.rilcallmediavideoflagparammask_2, RIL_CALLMEDIAVIDEOFLAG_TEMPORARILY_UNAVAILABLE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
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
req.lib: NtosKrnl.exe
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
-	RILCALLMEDIAVIDEOFLAGPARAMMASK
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIAVIDEOFLAGPARAMMASK
req.product: Windows 10 or later.
---

# RILCALLMEDIAVIDEOFLAGPARAMMASK enumeration


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef enum _RILCALLMEDIAVIDEOFLAGPARAMMASK { 
  RIL_CALLMEDIAVIDEOFLAG_CAPABILITY_UNKNOWN,
  RIL_CALLMEDIAVIDEOFLAG_PAUSE,
  RIL_CALLMEDIAVIDEOFLAG_TEMPORARILY_UNAVAILABLE,
  RIL_CALLMEDIAVIDEOFLAG_ALL
} RILCALLMEDIAVIDEOFLAGPARAMMASK;
````


## -enum-fields




### -field RIL_CALLMEDIAVIDEOFLAG_NONE



#### - RIL_CALLMEDIAVIDEOFLAG_CAPABILITY_UNKNOWN



#### - RIL_CALLMEDIAVIDEOFLAG_PAUSE



#### - RIL_CALLMEDIAVIDEOFLAG_TEMPORARILY_UNAVAILABLE



#### - RIL_CALLMEDIAVIDEOFLAG_ALL


