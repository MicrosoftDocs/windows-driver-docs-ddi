---
UID: NF:fcb.RxpReferenceNetFcb
title: RxpReferenceNetFcb function
author: windows-driver-content
description: RxpReferenceNetFcb increments the reference count on an FCB.
old-location: ifsk\rxpreferencenetfcb.htm
old-project: ifsk
ms.assetid: bc8999e2-d305-407f-8302-6834efa698c5
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: rxref_48d7801e-1459-405e-a681-2aa13e9e31cd.xml, RxpReferenceNetFcb function [Installable File System Drivers], fcb/RxpReferenceNetFcb, ifsk.rxpreferencenetfcb, RxpReferenceNetFcb
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Fcb.h
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
-	fcb.h
apiname:
-	RxpReferenceNetFcb
product: Windows
targetos: Windows
req.typenames: "*PFA_ENTRY, FA_ENTRY"
---

# RxpReferenceNetFcb function


## -description


<b>RxpReferenceNetFcb</b> increments the reference count on an FCB.


## -syntax


````
LONG RxpReferenceNetFcb(
   PFCB Fcb
);
````


## -parameters




### -param Fcb

A pointer to the FCB structure to be referenced.


## -returns



<b>RxpReferenceNetFcb</b> returns the final reference count after the reference. 




## -remarks



A number of debugging macros are defined in <i>fcb.h</i> that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxpReferenceNetFcb</b> or <b>RxpDereferenceNetFcb</b> routines used for file structure management operations on FCB structures. The <b>RxReferenceNetFcb</b> macro is the preferred way to call this routine. This macro first calls the <b>RxpTrackReference</b> routine to log diagnostic information about the request before calling the <b>RxpReferenceNetFcb</b> routine.

On checked builds, <b>RxpReferenceNetFcb</b> causes the system to ASSERT if the node type for the structure is not an FCB. 




## -see-also

<a href="..\fcb\nf-fcb-rxptrackreference.md">RxpTrackReference</a>



<a href="..\fcb\nf-fcb-rxptrackdereference.md">RxpTrackDereference</a>



<a href="..\fcb\nf-fcb-rxpdereferencenetfcb.md">RxpDereferenceNetFcb</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpReferenceNetFcb function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

