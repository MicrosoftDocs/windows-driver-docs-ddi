---
UID: NF:midatlax.RxReassociateMid
title: RxReassociateMid function (midatlax.h)
description: RxReassociateMid reassociates a Multiplex ID (MID) with an alternate context.
old-location: ifsk\rxreassociatemid.htm
tech.root: ifsk
ms.assetid: 2b80aa77-45b3-4157-8ab5-770c827a536a
ms.date: 04/16/2018
keywords: ["RxReassociateMid function"]
ms.keywords: RxReassociateMid, RxReassociateMid function [Installable File System Drivers], ifsk.rxreassociatemid, midatlax/RxReassociateMid, rxref_0fbfcaf6-383a-48ed-81b1-eed7521df3e7.xml
f1_keywords:
 - "midatlax/RxReassociateMid"
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
- RxReassociateMid
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxReassociateMid function


## -description


<b>RxReassociateMid</b> reassociates a Multiplex ID (MID) with an alternate context. 


## -parameters




### -param MidAtlas

<p>A pointer to the MID_ATLAS structure.</p>


### -param Mid

The multiplex ID to be mapped.


### -param NewContext

<p>A pointer that will hold the new context for this MID on exit.</p>




## -returns



<b>RxReassociateMid</b> returns STATUS_SUCCESS on success. The returned <i>pNewMid</i> parameter can be <b>NULL</b> if no context is associated with this MID.




## -remarks



RDBSS defines a MID as a 16-bit value, which can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxcreatemidatlas">RxCreateMidAtlas</a>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxassociatecontextwithmid">RxAssociateContextWithMid</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxcreatemidatlas">RxCreateMidAtlas</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxdestroymidatlas">RxDestroyMidAtlas</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxmapanddissociatemidfromcontext">RxMapAndDissociateMidFromContext</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxmapmidtocontext">RxMapMidToContext</a>
 

 

