---
UID: NS:ksmedia.TRANSPORT_STATE
title: TRANSPORT_STATE
author: windows-driver-content
description: The TRANSPORT_STATE structure
old-location: stream\transport_state.htm
old-project: stream
ms.assetid: 373fb91d-e469-4136-b2e3-bf57016c0fd6
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: stream.transport_state, vidcapstruct_5caaba9f-8a5c-4896-b181-c432a9678f58.xml, TRANSPORT_STATE structure [Streaming Media Devices], PTRANSPORT_STATE, *PTRANSPORT_STATE, ksmedia/TRANSPORT_STATE, PTRANSPORT_STATE structure pointer [Streaming Media Devices], TRANSPORT_STATE, ksmedia/PTRANSPORT_STATE
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ksmedia.h
req.include-header: Ksmedia.h
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
-	ksmedia.h
apiname:
-	TRANSPORT_STATE
product: Windows
targetos: Windows
req.typenames: "*PTRANSPORT_STATE, TRANSPORT_STATE"
---

# TRANSPORT_STATE structure


## -description


The TRANSPORT_STATE structure 


## -syntax


````
typedef struct {
  ULONG Mode;
  ULONG State;
} TRANSPORT_STATE, *PTRANSPORT_STATE;
````


## -struct-fields




### -field Mode

Specifies the mode of the external device transport.


### -field State

Specifies the state of the external device transport mode.


## -remarks


Any ED_Xxx tokens are defined in <i>xprtdefs.h</i> in the Microsoft DirectX SDK.

The following modes and states are used by <i>msdv.sys </i>and <i>mstape.sys</i>:

When <b>Mode</b> equals ED_MODE_RECORD, <b>State</b> may be:

ED_MODE_RECORD

ED_MODE_RECORD_FREEZE.

When <b>Mode</b> equals ED_MODE_PLAY, <b>State</b> may be:

ED_MODE_PLAY

ED_MODE_REV_PLAY

ED_MODE_STEP_FWD

ED_MODE_STEP_REV

ED_MODE_PLAY_SLOWEST_FWD

ED_MODE_PLAY_FASTEST_FWD

ED_MODE_PLAY_SLOWEST_REV

ED_MODE_PLAY_FASTEST_REV

ED_MODE_FREEZE

<b>Mode</b> equals <b>State</b> in the cases of:

ED_MODE_REW_FASTEST

ED_MODE_STOP

ED_MODE_PLAY

ED_MODE_FF


