---
UID: NS:ntddrilapitypes.RILSYSTEMSELECTIONPREFS_V2
title: RILSYSTEMSELECTIONPREFS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v2.htm
old-project: netvista
ms.assetid: 0734fac3-9327-4765-a50b-57be45ce2817
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS_V2, ,, 2, C, E, F, I, L, M, N, O, P, R, RILSYSTEMSELECTIONPREFS, RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2 structure [Network Drivers Starting with Windows Vista], S, T, V, Y, _, netvista.rilsystemselectionprefs_v2, ntddrilapitypes/RILSYSTEMSELECTIONPREFS_V2"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
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
-	ntddrilapitypes.h
apiname:
-	RILSYSTEMSELECTIONPREFS_V2
product: Windows
targetos: Windows
req.typenames: RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS
---

# RILSYSTEMSELECTIONPREFS_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSYSTEMSELECTIONPREFS_V2 {
  DWORD                               cbSize;
  DWORD                               dwParams;
  DWORD                               dwExecutor;
  DWORD                               dwSystemTypes;
  RILSYSTEMSELECTIONPREFSMODE         dwMode;
  RILOPERATORNAMES                    plmnInfo;
  RILSYSTEMSELECTIONPREFSROAMINGMODE  dwRoamingMode;
  DWORD                               dwAcquisitionOrderSize;
  DWORD [16]                          AcquisitionOrder;
} RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwSystemTypes


### -field dwMode


### -field plmnInfo


### -field dwRoamingMode


### -field dwAcquisitionOrderSize


### -field AcquisitionOrder

