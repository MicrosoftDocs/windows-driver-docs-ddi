---
UID: NF:midatlax.RxCreateMidAtlas
title: RxCreateMidAtlas function
author: windows-driver-content
description: RxCreateMidAtlas allocates a new instance of MID_ATLAS data structure and initializes it.
old-location: ifsk\rxcreatemidatlas.htm
old-project: ifsk
ms.assetid: 7c3fed89-a4e1-436f-9cbb-e140ad42bb13
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: RxCreateMidAtlas
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
req.alt-api: RxCreateMidAtlas
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

# RxCreateMidAtlas function



## -description
<b>RxCreateMidAtlas</b> allocates a new instance of MID_ATLAS data structure and initializes it. 



## -syntax

````
PRX_MID_ATLAS RxCreateMidAtlas(
   USHORT MaximumNumberOfMids,
   USHORT MidsAllocatedAtStart
);
````


## -parameters

### -param MaximumNumberOfMids 

The maximum number of multiplex IDs (MIDs) to be allowed in the atlas.


### -param MidsAllocatedAtStart 

The number of multiplex IDs allocated initially.


## -returns
<b>RxCreateMidAtlas</b> returns a pointer to allocated and initialized MID_ATLAS data structure on success or a <b>NULL</b> pointer on failure. 


## -remarks
RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. 

The MID must be efficiently able to manage the unique tagging and identification of a number of MIDs (typically 50) from a possible combination of 65,536 values. In order to ensure a proper time space tradeoff, the lookup is organized as a three level hierarchy. The 16 bits used to represent a MID are split up into three bitfields. The length of the rightmost field (least significant ) is decided by the maximum number of MIDs that are to be allowed in the atlas. This maximum value is a parameter passed to <b>RxCreateMidAtlas </b>when the MID_ATLAS data structure is created. The remaining length is split up equally between the next two fields. 

For example, if a maximum of 50 MIDs are to be allocated on creation , the length of the first field is 6 (64 ( 2 ** 6 ) is greater than 50 ). The remaining length is split into two fields of 5 bits each.

<b>RxCreateMidAtlas</b> allocates non-paged pool memory when creating a new MID_ATLAS data structure. 


## -see-also
<dl>
<dt>
<a href="..\midatlax\nf-midatlax-rxassociatecontextwithmid.md">RxAssociateContextWithMid</a>
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
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxCreateMidAtlas function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

