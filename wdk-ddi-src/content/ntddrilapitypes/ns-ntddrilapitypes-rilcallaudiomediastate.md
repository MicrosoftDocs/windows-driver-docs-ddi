---
UID: NS:ntddrilapitypes.RILCALLAUDIOMEDIASTATE
title: RILCALLAUDIOMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallaudiomediastate.htm
old-project: netvista
ms.assetid: f8e65085-6837-4d49-a39e-784942ee39a4
ms.author: windowsdriverdev
ms.date: 1/11/2018
ms.keywords: RILCALLAUDIOMEDIASTATE, RILCALLAUDIOMEDIASTATE, *LPRILCALLAUDIOMEDIASTATE
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
req.alt-api: RILCALLAUDIOMEDIASTATE
req.alt-loc: ntddrilapitypes.h
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
