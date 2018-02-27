---
UID: NS:rilapitypes.RILTONESIGNALINFO_V1
title: RILTONESIGNALINFO_V1
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\riltonesignalinfo_v1_2.htm
old-project: netvista
ms.assetid: c6685a19-73d3-4725-90b8-7c859791381a
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "*LPRILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1 structure [Network Drivers Starting with Windows Vista], netvista.riltonesignalinfo_v1_2, rilapitypes/RILTONESIGNALINFO_V1"
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
-	RILTONESIGNALINFO_V1
product: Windows
targetos: Windows
req.typenames: RILTONESIGNALINFO_V1, *LPRILTONESIGNALINFO_V1
req.product: Windows 10 or later.
---

# RILTONESIGNALINFO_V1 structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILTONESIGNALINFO_V1 {
  DWORD                 cbSize;
  DWORD                 dwParams;
  RIL3GPPTONE           dwGPPTone;
  RIL3GPP2TONE          dwGPP2Tone;
  RIL3GPP2ISDNALERTING  dwGPP2IsdnAlerting;
} RILTONESIGNALINFO_V1, RILTONESIGNALINFO_V1;
````


## -struct-fields




### -field cbSize


### -field dwParams


### -field dwGPPTone


### -field dwGPP2Tone


### -field dwGPP2IsdnAlerting

