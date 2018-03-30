---
UID: NF:midatlax.RxCreateMidAtlas
title: RxCreateMidAtlas function
author: windows-driver-content
description: RxCreateMidAtlas allocates a new instance of MID_ATLAS data structure and initializes it.
old-location: ifsk\rxcreatemidatlas.htm
old-project: ifsk
ms.assetid: 7c3fed89-a4e1-436f-9cbb-e140ad42bb13
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxCreateMidAtlas, RxCreateMidAtlas function [Installable File System Drivers], ifsk.rxcreatemidatlas, midatlax/RxCreateMidAtlas, rxref_539434e3-e1ea-4c97-b480-51bfe40eb44e.xml
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
-	RxCreateMidAtlas
product: Windows
targetos: Windows
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---

# RxCreateMidAtlas function


## -description


<b>RxCreateMidAtlas</b> allocates a new instance of MID_ATLAS data structure and initializes it. 


## -parameters




### -param MaximumNumberOfEntries

TBD


### -param InitialAllocation

TBD




#### - MaximumNumberOfMids

The maximum number of multiplex IDs (MIDs) to be allowed in the atlas.


#### - MidsAllocatedAtStart

The number of multiplex IDs allocated initially.


## -returns



<b>RxCreateMidAtlas</b> returns a pointer to allocated and initialized MID_ATLAS data structure on success or a <b>NULL</b> pointer on failure. 




## -remarks



RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. 

The MID must be efficiently able to manage the unique tagging and identification of a number of MIDs (typically 50) from a possible combination of 65,536 values. In order to ensure a proper time space tradeoff, the lookup is organized as a three level hierarchy. The 16 bits used to represent a MID are split up into three bitfields. The length of the rightmost field (least significant ) is decided by the maximum number of MIDs that are to be allowed in the atlas. This maximum value is a parameter passed to <b>RxCreateMidAtlas </b>when the MID_ATLAS data structure is created. The remaining length is split up equally between the next two fields. 

For example, if a maximum of 50 MIDs are to be allocated on creation , the length of the first field is 6 (64 ( 2 ** 6 ) is greater than 50 ). The remaining length is split into two fields of 5 bits each.

<b>RxCreateMidAtlas</b> allocates non-paged pool memory when creating a new MID_ATLAS data structure. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553388">RxAssociateContextWithMid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554395">RxDestroyMidAtlas</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554541">RxMapAndDissociateMidFromContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554545">RxMapMidToContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554686">RxReassociateMid</a>
 

 

