---
UID: NS:rilapitypes.RILTONESIGNALINFO_V2
title: RILTONESIGNALINFO_V2
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v2_2.htm
old-project: netvista
ms.assetid: 44508316-ff5c-48b0-9cdf-2d1aefa382c5
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: "*LPRILTONESIGNALINFO_V2, RILTONESIGNALINFO_V2, *LPRILTONESIGNALINFO, netvista.riltonesignalinfo_v2_2, RILTONESIGNALINFO_V2 structure [Network Drivers Starting with Windows Vista], rilapitypes/RILTONESIGNALINFO_V2, RILTONESIGNALINFO"
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
-	RILTONESIGNALINFO_V2
product: Windows
targetos: Windows
req.typenames: "*LPRILTONESIGNALINFO, RILTONESIGNALINFO, RILTONESIGNALINFO_V2, *LPRILTONESIGNALINFO_V2"
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


