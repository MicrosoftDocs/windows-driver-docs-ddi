---
UID: NS:rilapitypes.RILCALLMEDIASTATE
title: RILCALLMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediastate_2.htm
old-project: netvista
ms.assetid: d3b89502-667c-45dd-af1c-05b7c8613d6c
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: RILCALLMEDIASTATE, rilapitypes/RILCALLMEDIASTATE, RILCALLMEDIASTATE structure [Network Drivers Starting with Windows Vista], netvista.rilcallmediastate_2, *LPRILCALLMEDIASTATE
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
-	RILCALLMEDIASTATE
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMEDIASTATE, RILCALLMEDIASTATE"
req.product: Windows 10 or later.
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
  NULL                     switch_is;
  NULL                     dwCallMediaType;
  RILCALLAUDIOMEDIASTATE   stAudioState;
  NULL                     case;
  NULL                     RIL_CALLMEDIATYPE_AUDIO;
  RILCALLVIDEOMEDIASTATE   stVideoState;
  NULL                     case;
  NULL                     RIL_CALLMEDIATYPE_VIDEO;
  RILCALLCUSTOMMEDIASTATE  dwCustomStateSpecific;
  NULL                     case;
  NULL                     RIL_CALLMEDIATYPE_CUSTOM;
  DWORD [16]               pad;
  NULL                     case;
  NULL                     RIL_CALLMEDIATYPE_UNKNOWN;
} RILCALLMEDIASTATE, RILCALLMEDIASTATE;
````


## -struct-fields




### -field dwDirection


### -field dwCallMediaType


### -field mediaStateUnion


### -field mediaStateUnion.stAudioState

 


### -field mediaStateUnion.stVideoState

 


### -field mediaStateUnion.dwCustomStateSpecific

 


### -field mediaStateUnion.pad

 


### -field RILCALLMEDIASTATEUNION


#### - switch_is


#### - stAudioState


#### - case


#### - RIL_CALLMEDIATYPE_AUDIO


#### - stVideoState


#### - RIL_CALLMEDIATYPE_VIDEO


#### - dwCustomStateSpecific


#### - RIL_CALLMEDIATYPE_CUSTOM


#### - pad


#### - RIL_CALLMEDIATYPE_UNKNOWN

