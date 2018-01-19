---
UID: NS:rilapitypes.RILTONESIGNALINFO_V2
title: RILTONESIGNALINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v2_2.htm
old-project: netvista
ms.assetid: 44508316-ff5c-48b0-9cdf-2d1aefa382c5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILTONESIGNALINFO_V2, RILTONESIGNALINFO, *LPRILTONESIGNALINFO, *LPRILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2
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
req.alt-api: RILTONESIGNALINFO_V2
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
req.typenames: RILTONESIGNALINFO, *LPRILTONESIGNALINFO, *LPRILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2
req.product: Windows 10 or later.
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


## -remarks
