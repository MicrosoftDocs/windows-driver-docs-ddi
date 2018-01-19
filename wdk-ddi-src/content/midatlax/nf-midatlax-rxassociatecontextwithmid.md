---
UID: NF:midatlax.RxAssociateContextWithMid
title: RxAssociateContextWithMid function
author: windows-driver-content
description: RxAssociateContextWithMid associates the supplied opaque context with an available multiplex ID (MID) from a MID_ATLAS.
old-location: ifsk\rxassociatecontextwithmid.htm
old-project: ifsk
ms.assetid: b2ced4fb-5104-4bf3-8c6c-bf129e3dff97
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxAssociateContextWithMid
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
req.alt-api: RxAssociateContextWithMid
req.alt-loc: midatlax.h
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
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---

# RxAssociateContextWithMid function



## -description
<b>RxAssociateContextWithMid</b> associates the supplied opaque context with an available multiplex ID (MID) from a MID_ATLAS. 



## -syntax

````
NTSTATUS RxAssociateContextWithMid(
   PRX_MID_ATLAS pMidAtlas,
   PVOID         pContext,
   PUSHORT       pNewMid
);
````


## -parameters

### -param pMidAtlas 

A pointer to the MID_ATLAS data structure.


### -param pContext 

A pointer to the context.


### -param pNewMid 

A pointer to the multiplex ID to be associated with the context.


## -returns
<b>RxAssociateContextWithMid</b> returns STATUS_SUCCESS on success or one of the following error values: 
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>This error is returned when it was not possible to allocate sufficient memory for the new MID_MAP data structure.
<dl>
<dt><b>STATUS_UNSUCCESSFUL</b></dt>
</dl>This error is returned for several cases including when the number of MIDs already in use is greater than the maximum number of MIDs set when the MID_ATLAS structure was created.

 


## -remarks
RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. <b>RxAssociateContextWithMid</b> allocates non-paged pool memory when creating a new MID_MAP data structure.

The <i>pContext</i> parameter can be any opaque context but it is commonly an RX_CONTEXT. 


## -see-also
<dl>
<dt>
<a href="..\midatlax\nf-midatlax-rxcreatemidatlas.md">RxCreateMidAtlas</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxdestroymidatlas.md">RxDestroyMidAtlas</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxmapmidtocontext.md">RxMapMidToContext</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxmapanddissociatemidfromcontext.md">RxMapAndDissociateMidFromContext</a>
</dt>
<dt>
<a href="..\midatlax\nf-midatlax-rxreassociatemid.md">RxReassociateMid</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxAssociateContextWithMid function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

