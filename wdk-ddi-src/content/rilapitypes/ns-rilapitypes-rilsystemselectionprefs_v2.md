---
UID: NS:rilapitypes.RILSYSTEMSELECTIONPREFS_V2
title: RILSYSTEMSELECTIONPREFS_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsystemselectionprefs_v2_2.htm
old-project: netvista
ms.assetid: d5866096-9df6-4453-96ab-8abd16707afc
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILSYSTEMSELECTIONPREFS_V2, *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS
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
req.alt-api: RILSYSTEMSELECTIONPREFS_V2
req.alt-loc: rilapitypes.h
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
req.typenames: *LPRILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS_V2, RILSYSTEMSELECTIONPREFS, *LPRILSYSTEMSELECTIONPREFS
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


## -remarks
