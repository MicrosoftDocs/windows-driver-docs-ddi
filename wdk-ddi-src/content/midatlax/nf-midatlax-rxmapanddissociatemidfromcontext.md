---
UID: NF:midatlax.RxMapAndDissociateMidFromContext
title: RxMapAndDissociateMidFromContext function
author: windows-driver-content
description: RxMapAndDissociateMidFromContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context.
old-location: ifsk\rxmapanddissociatemidfromcontext.htm
old-project: ifsk
ms.assetid: e9021983-8a01-4262-ae3f-c265948d5a2c
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: RxMapAndDissociateMidFromContext, RxMapAndDissociateMidFromContext function [Installable File System Drivers], ifsk.rxmapanddissociatemidfromcontext, midatlax/RxMapAndDissociateMidFromContext, rxref_919dabed-ac8c-4495-8709-8fb45280e16f.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: midatlax.h
req.include-header: Midatlax.h
req.target-type: Desktop
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
req.irql: "<= APC_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	midatlax.h
api_name:
-	RxMapAndDissociateMidFromContext
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxMapAndDissociateMidFromContext function


## -description


<b>RxMapAndDissociateMidFromContext</b> maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context. 


## -parameters




### -param MidAtlas

TBD


### -param Mid

The multiplex ID to be mapped.


### -param ContextPointer

TBD




#### - pContextPointer

A pointer that will hold the context for this MID on exit.


#### - pMidAtlas

A pointer to the MID_ATLAS structure.


## -returns




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554686">RxReassociateMid</a>
      always returns STATUS_SUCCESS. 

The returned <i>pContextPointer</i> parameter is a pointer to the associated context, or a <b>NULL</b> if no context was associated with this MID.




## -remarks



RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553388">RxAssociateContextWithMid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554352">RxCreateMidAtlas</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554395">RxDestroyMidAtlas</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554545">RxMapMidToContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554686">RxReassociateMid</a>
 

 

