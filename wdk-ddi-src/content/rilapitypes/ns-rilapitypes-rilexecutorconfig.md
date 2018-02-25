---
UID: NS:rilapitypes.RILEXECUTORCONFIG
title: RILEXECUTORCONFIG
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilexecutorconfig_2.htm
old-project: netvista
ms.assetid: 8f10bb0f-2a9e-4310-946d-c1c9250391e7
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILEXECUTORCONFIG, ,, C, E, F, G, I, L, N, O, P, R, RILEXECUTORCONFIG, RILEXECUTORCONFIG structure [Network Drivers Starting with Windows Vista], T, U, X, netvista.rilexecutorconfig_2, rilapitypes/RILEXECUTORCONFIG"
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
-	RILEXECUTORCONFIG
product: Windows
targetos: Windows
req.typenames: RILEXECUTORCONFIG, *LPRILEXECUTORCONFIG
req.product: Windows 10 or later.
---

# RILEXECUTORCONFIG structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILEXECUTORCONFIG {
  DWORD                           cbSize;
  DWORD                           dwFlags;
  DWORD                           dwNumApps;
  HUICCAPP [MAXNUM_EXECUTOR_APPS] lphUiccApps;
} RILEXECUTORCONFIG, RILEXECUTORCONFIG;
````


## -struct-fields




### -field cbSize


### -field dwFlags


### -field dwNumApps


### -field lphUiccApps

