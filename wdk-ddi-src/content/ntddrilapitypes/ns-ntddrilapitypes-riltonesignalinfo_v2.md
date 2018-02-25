---
UID: NS:ntddrilapitypes.RILTONESIGNALINFO_V2
title: RILTONESIGNALINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v2.htm
old-project: netvista
ms.assetid: e0c40d65-d290-4fae-9fa7-57a9bf047f13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , *, *LPRILTONESIGNALINFO, *LPRILTONESIGNALINFO_V2, ,, 2, A, E, F, G, I, L, N, O, P, R, RILTONESIGNALINFO, RILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2 structure [Network Drivers Starting with Windows Vista], S, T, V, _, netvista.riltonesignalinfo_v2, ntddrilapitypes/RILTONESIGNALINFO_V2"
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
-	RILTONESIGNALINFO_V2
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFO_V2, *LPRILTONESIGNALINFO_V2, RILTONESIGNALINFO, *LPRILTONESIGNALINFO
---

# RILTONESIGNALINFO_V2 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILTONESIGNALINFO_V2 {
  DWORD                 cbSize;
  DWORD                 dwParams;
  DWORD                 dwExecutor;
  RIL3GPPTONE           dwGPPTone;
  RIL3GPP2TONE          dwGPP2Tone;
  RIL3GPP2ISDNALERTING  dwGPP2IsdnAlerting;
} RILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwExecutor


### -field dwGPPTone


### -field dwGPP2Tone


### -field dwGPP2IsdnAlerting

