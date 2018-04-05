---
UID: NF:midatlax.RxMapMidToContext
title: RxMapMidToContext function
author: windows-driver-content
description: RxMapMidToContext maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure.
old-location: ifsk\rxmapmidtocontext.htm
old-project: ifsk
ms.assetid: e0625c27-6de9-401f-a6bd-52697c4a57c0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxMapMidToContext, RxMapMidToContext function [Installable File System Drivers], ifsk.rxmapmidtocontext, midatlax/RxMapMidToContext, rxref_e7a11999-7ace-4154-91aa-28dc99a83790.xml
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
-	RxMapMidToContext
product:
- Windows
targetos: Windows
req.typenames: MCD_INIT_DATA, *PMCD_INIT_DATA
---

# RxMapMidToContext function


## -description


<b>RxMapMidToContext</b> maps a Multiplex ID (MID) to its associated context in a MID_ATLAS structure. 


## -parameters




### -param MidAtlas

TBD


### -param Mid

The multiplex ID to be mapped.


#### - pMidAtlas

A pointer to the MID_ATLAS structure.


## -returns



<b>RxMapMidToContext</b> returns a pointer to the associated context, or <b>NULL</b> if none exists.




## -remarks



RDBSS defines a Multiplex ID (MID), a 16-bit value, that can be used by both the network client (mini-redirector) and the server to distinguish between the concurrently active requests on any connection. A MID is a component of a MID_ATLAS data structure allocated by calling <b>RxCreateMidAtlas</b>. A MID_MAP data structure is allocated and used for mapping MIDs to RX_CONTEXT data structures. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff553388">RxAssociateContextWithMid</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554352">RxCreateMidAtlas</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554395">RxDestroyMidAtlas</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554541">RxMapAndDissociateMidFromContext</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff554686">RxReassociateMid</a>
 

 

