---
UID: NF:rxprocs.RxReference
title: RxReference function
author: windows-driver-content
description: RxReference increments the NodeReferenceCount member of a structure by one for several of the reference counted data structures used by RDBSS.
old-location: ifsk\rxreference.htm
old-project: ifsk
ms.assetid: 436cd161-6984-4101-931a-221a829f40d0
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxreference, rxref_3c87a6aa-d0c8-4308-8152-fce322dcb035.xml, RxReference function [Installable File System Drivers], rxprocs/RxReference, RxReference
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
req.lib: NtosKrnl.exe
req.dll: 
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	rxprocs.h
apiname:
-	RxReference
product: Windows
targetos: Windows
req.typenames: RX_CONTEXT, *PRX_CONTEXT
req.product: Windows 10 or later.
---

# RxReference function


## -description


<b>RxReference</b> increments the <b>NodeReferenceCount</b> member of a structure by one for several of the reference counted data structures used by RDBSS. 


## -syntax


````
VOID RxReference(
  _Inout_ PVOID Instance
);
````


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

<a href="..\rxprocs\nf-rxprocs-rxdereference.md">RxDereference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxReference function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

