---
UID: NS:rilapitypes.RILCALLAUDIOMEDIASTATE
title: RILCALLAUDIOMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastate_2.htm
old-project: netvista
ms.assetid: f15f609d-605b-4f4c-8f57-01c6b426d8b5
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE, *LPRILCALLAUDIOMEDIASTATE
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
req.alt-api: RILCALLAUDIOMEDIASTATE
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


## -remarks
