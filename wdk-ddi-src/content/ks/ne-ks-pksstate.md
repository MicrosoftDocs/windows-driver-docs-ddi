---
UID: NE:ks.PKSSTATE
title: "*PKSSTATE"
author: windows-driver-content
description: The KSSTATE enumeration lists possible states of a kernel streaming object.
old-location: stream\ksstate.htm
old-project: stream
ms.assetid: 6f5a3c65-9d6c-4d5f-af99-71aba16eb254
ms.author: windowsdriverdev
ms.date: 2/20/2018
ms.keywords: KSSTATE_ACQUIRE, KSSTATE_RUN, KSSTATE, PKSSTATE enumeration pointer [Streaming Media Devices], ks-struct_a5862576-6737-471e-8e31-1bc98fb4b4f9.xml, ks/KSSTATE_RUN, ks/PKSSTATE, PKSSTATE, KSSTATE_STOP, stream.ksstate, ks/KSSTATE_ACQUIRE, KSSTATE_PAUSE, *PKSSTATE, KSSTATE enumeration [Streaming Media Devices], ks/KSSTATE_STOP, ks/KSSTATE_PAUSE, ks/KSSTATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: enum
req.header: ks.h
req.include-header: Ks.h
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
-	ks.h
apiname:
-	KSSTATE
product: Windows
targetos: Windows
req.typenames: KSSTATE, *PKSSTATE
---

# *PKSSTATE enumeration


## -description


The KSSTATE enumeration lists possible states of a kernel streaming object.


## -syntax


````
typedef enum  { 
  KSSTATE_STOP     = 0,
  KSSTATE_ACQUIRE  = 1,
  KSSTATE_PAUSE    = 2,
  KSSTATE_RUN      = 3
} KSSTATE, *PKSSTATE;
````


## -enum-fields




### -field KSSTATE_STOP

Indicates that the object is in minimum resource consumption mode.


### -field KSSTATE_ACQUIRE

Indicates that the object is acquiring resources.


### -field KSSTATE_PAUSE

Indicates that the object is preparing to make instant transition to Run state.


### -field KSSTATE_RUN

Indicates that the object is actively streaming.

