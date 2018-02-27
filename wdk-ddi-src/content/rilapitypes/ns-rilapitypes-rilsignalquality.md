---
UID: NS:rilapitypes.RILSIGNALQUALITY
title: RILSIGNALQUALITY
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilsignalquality_2.htm
old-project: netvista
ms.assetid: cc5bf370-3996-46de-b27d-8a390a6f407e
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILSIGNALQUALITY, RILSIGNALQUALITY, RILSIGNALQUALITY structure [Network Drivers Starting with Windows Vista], netvista.rilsignalquality_2, rilapitypes/RILSIGNALQUALITY"
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
-	RILSIGNALQUALITY
product: Windows
targetos: Windows
req.typenames: RILSIGNALQUALITY, *LPRILSIGNALQUALITY
req.product: Windows 10 or later.
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

