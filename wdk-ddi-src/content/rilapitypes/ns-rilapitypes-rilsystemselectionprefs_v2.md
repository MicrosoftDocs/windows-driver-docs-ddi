---
UID: NS:rilapitypes.RILSYSTEMSELECTIONPREFS_V2
title: RILSYSTEMSELECTIONPREFS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v2_2.htm
old-project: netvista
ms.assetid: d5866096-9df6-4453-96ab-8abd16707afc
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILSYSTEMSELECTIONPREFS_V2 structure [Network Drivers Starting with Windows Vista], netvista.rilsystemselectionprefs_v2_2, rilapitypes/RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS, RILSYSTEMSELECTIONPREFS
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
-	RILSYSTEMSELECTIONPREFS_V2
product: Windows
targetos: Windows
req.typenames: RILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS
req.product: Windows 10 or later.
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
  DWORD [MAXLENGTH_ACQUISITIONORDER]  AcquisitionOrder;
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

