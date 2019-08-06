---
UID: NF:midatlax.RxMapAndDissociateMidFromContext
title: RxMapAndDissociateMidFromContext function (midatlax.h)
description: RxMapAndDissociateMidFromContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure and then disassociates the MID from the context.
old-location: ifsk\rxmapanddissociatemidfromcontext.htm
tech.root: ifsk
ms.assetid: e9021983-8a01-4262-ae3f-c265948d5a2c
ms.date: 04/16/2018
ms.keywords: RxMapAndDissociateMidFromContext, RxMapAndDissociateMidFromContext function [Installable File System Drivers], ifsk.rxmapanddissociatemidfromcontext, midatlax/RxMapAndDissociateMidFromContext, rxref_919dabed-ac8c-4495-8709-8fb45280e16f.xml
ms.topic: function
f1_keywords:
 - "midatlax/RxMapAndDissociateMidFromContext"
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- midatlax.h
api_name:
- RxMapAndDissociateMidFromContext
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

<p>A pointer to the MID_ATLAS structure.</p>


### -param Mid

The multiplex ID to be mapped.


### -param ContextPointer

<p>A pointer that will hold the context for this MID on exit.</p>




## -returns




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/midatlax/nf-midatlax-rxreassociatemid">RxReassociateMid</a>
      always returns STATUS_SUCCESS. 

The returned <i>pContextPointer</i> parameter is a pointer to the associated context, or a <b>NULL</b> if no context was associated with this MID.




## -remarks



RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/midatlax/nf-midatlax-rxassociatecontextwithmid">RxAssociateContextWithMid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/midatlax/nf-midatlax-rxcreatemidatlas">RxCreateMidAtlas</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/midatlax/nf-midatlax-rxdestroymidatlas">RxDestroyMidAtlas</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/midatlax/nf-midatlax-rxmapmidtocontext">RxMapMidToContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/midatlax/nf-midatlax-rxreassociatemid">RxReassociateMid</a>
 

 

