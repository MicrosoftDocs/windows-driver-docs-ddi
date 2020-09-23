---
UID: NF:midatlax.RxMapMidToContext
title: RxMapMidToContext function (midatlax.h)
description: RxMapMidToContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure.
old-location: ifsk\rxmapmidtocontext.htm
tech.root: ifsk
ms.assetid: e0625c27-6de9-401f-a6bd-52697c4a57c0
ms.date: 04/16/2018
keywords: ["RxMapMidToContext function"]
ms.keywords: RxMapMidToContext, RxMapMidToContext function [Installable File System Drivers], ifsk.rxmapmidtocontext, midatlax/RxMapMidToContext, rxref_e7a11999-7ace-4154-91aa-28dc99a83790.xml
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
targetos: Windows
req.typenames: 
f1_keywords:
 - RxMapMidToContext
 - midatlax/RxMapMidToContext
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - midatlax.h
api_name:
 - RxMapMidToContext
---

# RxMapMidToContext function


## -description

<b>RxMapMidToContext</b> maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure.

## -parameters

### -param MidAtlas

<p>A pointer to the MID_ATLAS structure.</p>

### -param Mid

The multiplex ID to be mapped.

## -returns

<b>RxMapMidToContext</b> returns a pointer to the associated context, or <b>NULL</b> if none exists.

## -remarks

RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures.

## -see-also

<a href="/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxassociatecontextwithmid">RxAssociateContextWithMid</a>



<a href="/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxcreatemidatlas">RxCreateMidAtlas</a>



<a href="/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxdestroymidatlas">RxDestroyMidAtlas</a>



<a href="/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxmapanddissociatemidfromcontext">RxMapAndDissociateMidFromContext</a>



<a href="/windows-hardware/drivers/ddi/midatlax/nf-midatlax-rxreassociatemid">RxReassociateMid</a>