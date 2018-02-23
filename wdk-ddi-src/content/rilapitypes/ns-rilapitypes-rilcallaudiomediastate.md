---
UID: NS:rilapitypes.RILCALLAUDIOMEDIASTATE
title: RILCALLAUDIOMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastate_2.htm
old-project: netvista
ms.assetid: f15f609d-605b-4f4c-8f57-01c6b426d8b5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: netvista.rilcallaudiomediastate_2, rilapitypes/RILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE structure [Network Drivers Starting with Windows Vista], *LPRILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE
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
-	RILCALLAUDIOMEDIASTATE
product: Windows
targetos: Windows
req.typenames: RILCALLAUDIOMEDIASTATE, *LPRILCALLAUDIOMEDIASTATE
req.product: Windows 10 or later.
---

# RILCALLAUDIOMEDIASTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code. 


## -syntax


````
typedef struct _RILCALLAUDIOMEDIASTATE {
  DWORD                dwParams;
  RILCALLAUDIOSOURCE   dwAudioSource;
  RILCALLAUDIOQUALITY  dwAudioQuality;
  DWORD                dwFlags;
} RILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE;
````


## -struct-fields




### -field dwParams


### -field dwAudioSource


### -field dwAudioQuality


### -field dwFlags

