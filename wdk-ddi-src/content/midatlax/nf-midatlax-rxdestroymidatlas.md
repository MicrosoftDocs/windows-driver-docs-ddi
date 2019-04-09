---
UID: NF:midatlax.RxDestroyMidAtlas
title: RxDestroyMidAtlas function (midatlax.h)
description: RxDestroyMidAtlas destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory.
old-location: ifsk\rxdestroymidatlas.htm
tech.root: ifsk
ms.assetid: 9d5c08c8-8306-46e3-b10b-eeefe473d340
ms.date: 04/16/2018
ms.keywords: RxDestroyMidAtlas, RxDestroyMidAtlas function [Installable File System Drivers], ifsk.rxdestroymidatlas, midatlax/RxDestroyMidAtlas, rxref_3a954108-5744-4b47-87b7-7553d64ec038.xml
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- midatlax.h
api_name:
- RxDestroyMidAtlas
product:
- Windows
targetos: Windows
req.typenames: 
---

# RxDestroyMidAtlas function


## -description


<b>RxDestroyMidAtlas</b> destroys an existing instance of a MID_ATLAS data structure and frees the allocated memory. 


## -parameters




### -param MidAtlas

<p>The MID_ATLAS structure to be freed.</p>


### -param ContextDestructor

<p>An associated context destructor.</p>




## -returns



None 




## -remarks



RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is part of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>.

<b>RxDestroyMidAtlas</b> destroys a MID_ATLAS data structure previously created by a call to <b>RxCreateMidAtlas</b>. As a side effect, <b>RxDestroyMidAtlas</b> invokes the passed in context destructor on every valid context in the MID_ATLAS. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553388">RxAssociateContextWithMid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554352">RxCreateMidAtlas</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554541">RxMapAndDissociateMidFromContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554545">RxMapMidToContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554686">RxReassociateMid</a>
 

 

