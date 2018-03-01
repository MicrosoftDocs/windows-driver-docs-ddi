---
UID: NS:ntddrilapitypes.RILCALLMEDIASTATE
title: RILCALLMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediastate.htm
old-project: netvista
ms.assetid: 1fe4b90e-f89a-4ccc-bc92-b6f2edfb0b98
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPRILCALLMEDIASTATE, RILCALLMEDIASTATE, RILCALLMEDIASTATE structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediastate, ntddrilapitypes/RILCALLMEDIASTATE"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	ntddrilapitypes.h
api_name:
-	RILCALLMEDIASTATE
product: Windows
targetos: Windows
req.typenames: RILCALLMEDIASTATE, *LPRILCALLMEDIASTATE
---

# RILCALLMEDIASTATE structure


## -description


This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.


## -syntax


````
typedef struct _RILCALLMEDIASTATE {
  RILCALLMEDIADIRECTION    dwDirection;
  RILCALLMEDIATYPE         dwCallMediaType;
  NULL                     RILCALLMEDIASTATEUNION;
  RILCALLMEDIASTATEUNION   mediaStateUnion;
  RILCALLAUDIOMEDIASTATE   stAudioState;
  RILCALLVIDEOMEDIASTATE   stVideoState;
  RILCALLCUSTOMMEDIASTATE  dwCustomStateSpecific;
  DWORD [16]               pad;
} RILCALLMEDIASTATE, RILCALLMEDIASTATE;
````


## -struct-fields




### -field dwDirection


### -field dwCallMediaType


### -field mediaStateUnion


### -field RILCALLMEDIASTATEUNION


#### - stAudioState


#### - stVideoState


#### - dwCustomStateSpecific


#### - pad

