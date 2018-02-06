---
UID: NS:ntddrilapitypes.RILCALLMEDIASTATE
title: RILCALLMEDIASTATE
author: windows-driver-content
description: This topic supports the Windows driver infrastructure and is not intended to be used directly from your code.
old-location: netvista\rilcallmediastate.htm
old-project: netvista
ms.assetid: 1fe4b90e-f89a-4ccc-bc92-b6f2edfb0b98
ms.author: windowsdriverdev
ms.date: 1/18/2018
ms.keywords: netvista.rilcallmediastate, RILCALLMEDIASTATE structure [Network Drivers Starting with Windows Vista], *LPRILCALLMEDIASTATE, ntddrilapitypes/RILCALLMEDIASTATE, RILCALLMEDIASTATE
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
-	RILCALLMEDIASTATE
product: Windows
targetos: Windows
req.typenames: "*LPRILCALLMEDIASTATE, RILCALLMEDIASTATE"
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




### -field mediaStateUnion



### -field mediaStateUnion.stAudioState

 


### -field mediaStateUnion.stVideoState

 


### -field mediaStateUnion.dwCustomStateSpecific

 


### -field mediaStateUnion.pad

 


### -field RILCALLMEDIASTATEUNION



### -field dwDirection



### -field dwCallMediaType



#### - stAudioState



#### - stVideoState



#### - dwCustomStateSpecific



#### - pad


