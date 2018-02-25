---
UID: NS:rilapitypes.RILRFSTATE
title: RILRFSTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilrfstate_2.htm
old-project: netvista
ms.assetid: 1e185734-21d9-4047-9e74-cf5a765857ed
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILRFSTATE, ,, A, E, F, I, L, P, R, RILRFSTATE, RILRFSTATE structure [Network Drivers Starting with Windows Vista], S, T, netvista.rilrfstate_2, rilapitypes/RILRFSTATE"
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
-	RILRFSTATE
product: Windows
targetos: Windows
req.typenames: RILRFSTATE, *LPRILRFSTATE
req.product: Windows 10 or later.
---

# RILRFSTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILRFSTATE {
  DWORD    cbSize;
  DWORD    dwParams;
  DWORD    dwRFState;
  DWORD    dwRFDataSize;
  BYTE [1] bRFData;
} RILRFSTATE, RILRFSTATE;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwRFState


### -field dwRFDataSize


### -field bRFData

