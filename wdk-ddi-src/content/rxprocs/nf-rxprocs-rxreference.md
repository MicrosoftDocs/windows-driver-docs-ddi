---
UID: NF:rxprocs.RxReference
title: RxReference function
author: windows-driver-content
description: RxReference increments the NodeReferenceCount member of a structure by one for several of the reference counted data structures used by RDBSS.
old-location: ifsk\rxreference.htm
old-project: ifsk
ms.assetid: 436cd161-6984-4101-931a-221a829f40d0
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: RxReference, RxReference function [Installable File System Drivers], ifsk.rxreference, rxprocs/RxReference, rxref_3c87a6aa-d0c8-4308-8152-fce322dcb035.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: rxprocs.h
req.include-header: Rxprocs.h
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
-	rxprocs.h
api_name:
-	RxReference
product:
- Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxReference function


## -description


<b>RxReference</b> increments the <b>NodeReferenceCount</b> member of a structure by one for several of the reference counted data structures used by RDBSS. 


## -parameters




### -param Instance [in, out]

A pointer to the reference-counted data structure to be referenced (incremented). 


## -returns



None 




## -remarks



The <b>RxReference</b> routine can be used to reference (increment by one) the <b>NodeReferenceCount</b> member on the following data structures used by RDBSS:

SRV_CALL

NET_ROOT

V_NET_ROOT

SRV_OPEN

FOBX

If <b>RxReference</b> is called with any other type of RDBSS data structure, the routine causes the system to ASSERT on checked builds. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff554388">RxDereference</a>
 

 

