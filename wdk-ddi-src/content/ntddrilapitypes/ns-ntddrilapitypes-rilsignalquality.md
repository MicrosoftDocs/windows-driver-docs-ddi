---
UID: NS:ntddrilapitypes.RILSIGNALQUALITY
title: RILSIGNALQUALITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalquality.htm
old-project: netvista
ms.assetid: b2edfcdb-28b9-4322-8bfb-4d5d2c2d1519
ms.author: windowsdriverdev
ms.date: 2/27/2018
ms.keywords: "*LPRILSIGNALQUALITY, RILSIGNALQUALITY, RILSIGNALQUALITY structure [Network Drivers Starting with Windows Vista], netvista.rilsignalquality, ntddrilapitypes/RILSIGNALQUALITY"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddrilapitypes.h
req.include-header: Rilapitypes.h
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
-	ntddrilapitypes.h
api_name:
-	RILSIGNALQUALITY
product: Windows
targetos: Windows
req.typenames: RILSIGNALQUALITY, *LPRILSIGNALQUALITY
---

# RILSIGNALQUALITY structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILSIGNALQUALITY {
  DWORD  cbSize;
  DWORD  dwParams;
  DWORD  dwExecutor;
  DWORD  dwSystemType;
  int    nNumSignalBars;
  int    nSignalStrength;
  int    nSNRStrength;
} RILSIGNALQUALITY, RILSIGNALQUALITY;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwSystemType


### -field nNumSignalBars


### -field nSignalStrength


### -field nSNRStrength

