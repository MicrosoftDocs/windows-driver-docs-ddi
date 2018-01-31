---
UID: NF:fltkernel.FltObjectDereference
title: FltObjectDereference function
author: windows-driver-content
description: The FltObjectDereference routine removes a rundown reference from an opaque filter, instance, or volume pointer.
old-location: ifsk\fltobjectdereference.htm
old-project: ifsk
ms.assetid: d4add891-e90e-4fad-b862-c5cad91a277d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: FltObjectDereference, fltkernel/FltObjectDereference, ifsk.fltobjectdereference, FltApiRef_e_to_o_4fbb4535-c814-4af7-b68d-f0d66da9bae2.xml, FltObjectDereference routine [Installable File System Drivers]
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltObjectDereference
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltObjectDereference function


## -description


The <b>FltObjectDereference</b> routine removes a rundown reference from an opaque filter, instance, or volume pointer. 


## -syntax


````
VOID FltObjectDereference(
  _Inout_ PVOID FltObject
);
````


## -parameters




#### - FltObject [in, out]

Opaque filter pointer (PFLT_FILTER), instance pointer (PFLT_INSTANCE), or volume pointer (PFLT_VOLUME). 


## -returns


None 



## -remarks


To add a rundown reference to an opaque filter, instance, or volume pointer, call <a href="..\fltkernel\nf-fltkernel-fltobjectreference.md">FltObjectReference</a>. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltobjectreference.md">FltObjectReference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltObjectDereference routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

