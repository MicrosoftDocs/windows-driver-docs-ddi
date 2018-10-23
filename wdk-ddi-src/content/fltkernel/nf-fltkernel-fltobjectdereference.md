---
UID: NF:fltkernel.FltObjectDereference
title: FltObjectDereference function
author: windows-driver-content
description: The FltObjectDereference routine removes a rundown reference from an opaque filter, instance, or volume pointer.
old-location: ifsk\fltobjectdereference.htm
tech.root: ifsk
ms.assetid: d4add891-e90e-4fad-b862-c5cad91a277d
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_4fbb4535-c814-4af7-b68d-f0d66da9bae2.xml, FltObjectDereference, FltObjectDereference routine [Installable File System Drivers], fltkernel/FltObjectDereference, ifsk.fltobjectdereference
ms.topic: function
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: "<= DISPATCH_LEVEL"
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltObjectDereference
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltObjectDereference function


## -description


The <b>FltObjectDereference</b> routine removes a rundown reference from an opaque filter, instance, or volume pointer. 


## -parameters




### -param FltObject [in, out]

Opaque filter pointer (PFLT_FILTER), instance pointer (PFLT_INSTANCE), or volume pointer (PFLT_VOLUME). 


## -returns



None 




## -remarks



To add a rundown reference to an opaque filter, instance, or volume pointer, call <a href="https://msdn.microsoft.com/library/windows/hardware/ff543382">FltObjectReference</a>. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff543382">FltObjectReference</a>
 

 

