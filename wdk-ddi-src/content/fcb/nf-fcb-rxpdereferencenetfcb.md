---
UID: NF:fcb.RxpDereferenceNetFcb
title: RxpDereferenceNetFcb function
author: windows-driver-content
description: RxpDereferenceNetFcb decrements the reference count on an FCB structure.
old-location: ifsk\rxpdereferencenetfcb.htm
old-project: ifsk
ms.assetid: 6e59a1c7-ddd4-40a6-8e75-879cbef010db
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: RxpDereferenceNetFcb, RxpDereferenceNetFcb function [Installable File System Drivers], fcb/RxpDereferenceNetFcb, ifsk.rxpdereferencenetfcb, rxref_5b67e32d-12f2-4c52-9099-16505e00233f.xml
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	fcb.h
api_name:
-	RxpDereferenceNetFcb
product: Windows
targetos: Windows
req.typenames: FA_ENTRY, *PFA_ENTRY
---

# RxpDereferenceNetFcb function


## -description


<b>RxpDereferenceNetFcb</b> decrements the reference count on an FCB structure.


## -syntax


````
LONG RxpDereferenceNetFcb(
   PFCB Fcb
);
````


## -parameters




### -param Fcb

A pointer to the FCB structure to be dereferenced.


## -returns



<b>RxpDereferenceNetFcb</b> returns the final reference count after the dereference. 




## -remarks



The referencing and dereferencing of FCBs is different from those of the other data structures because of the embedded resource in the FCB. This implies that the caller requires information regarding the status of the FCB (whether it was finalized or not ). To finalize the FCB, two locks need to be held, the NET_ROOT name table lock as well as the FCB resource. These considerations lead to a different approach in dereferencing FCBs. Consequently, <b>RxpDereferenceNetFcb</b> does not attempt to finalize the FCB.

A number of macros are defined in <i>fcb.h</i> for debugging that are the preferred way to call this routine. These macros provide a wrapper around the <b>RxpReferenceNetFcb</b>  or <b>RxpDereferenceNetFcb</b> routines used for file structure management operations on FCB structures. The <b>RxDereferenceNetFcb</b> macro is the preferred way to call this routine. This macro first calls the <b>RxpTrackDereference</b> routine to log diagnostic information about the request before calling the <b>RxpDereferenceNetFcb</b> routine.

On checked builds, <b>RxpDereferenceNetFcb</b> causes the system to ASSERT if the node type for the structure is not an FCB or if the final reference count is less than 0. 




## -see-also

<a href="..\fcb\nf-fcb-rxptrackreference.md">RxpTrackReference</a>



<a href="..\fcb\nf-fcb-rxptrackdereference.md">RxpTrackDereference</a>



<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>



<a href="https://docs.microsoft.com/en-us/windows-hardware/drivers/ifs/the-fcb-structure">The FCB Structure</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpDereferenceNetFcb function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

