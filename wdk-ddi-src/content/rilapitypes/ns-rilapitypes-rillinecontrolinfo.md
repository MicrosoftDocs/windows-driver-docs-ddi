---
UID: NS:rilapitypes.RILLINECONTROLINFO
title: RILLINECONTROLINFO
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rillinecontrolinfo_2.htm
old-project: netvista
ms.assetid: 490ef6ed-c5df-450f-acd1-36091ac8999e
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILLINECONTROLINFO, RILLINECONTROLINFO, RILLINECONTROLINFO structure [Network Drivers Starting with Windows Vista], netvista.rillinecontrolinfo_2, rilapitypes/RILLINECONTROLINFO"
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
-	RILLINECONTROLINFO
product: Windows
targetos: Windows
req.typenames: RILLINECONTROLINFO, *LPRILLINECONTROLINFO
req.product: Windows 10 or later.
---

# RILLINECONTROLINFO structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILLINECONTROLINFO {
  DWORD  cbSize;
  DWORD  dwExecutor;
  BOOL   fPolarityIncluded;
  BOOL   fToggleMode;
  BOOL   fReversePolarity;
  DWORD  dwPowerDenialTime;
} RILLINECONTROLINFO, RILLINECONTROLINFO;
````


## -struct-fields




### -field cbSize


### -field dwExecutor


### -field fPolarityIncluded


### -field fToggleMode


### -field fReversePolarity


### -field dwPowerDenialTime

