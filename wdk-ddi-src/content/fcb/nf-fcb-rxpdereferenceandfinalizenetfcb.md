---
UID: NF:fcb.RxpDereferenceAndFinalizeNetFcb
title: RxpDereferenceAndFinalizeNetFcb function
author: windows-driver-content
description: RxpDereferenceAndFinalizeNetFcb decrements the reference count and finalizes an FCB structure.
old-location: ifsk\rxpdereferenceandfinalizenetfcb.htm
old-project: ifsk
ms.assetid: 954a4811-4515-4ed4-a4f1-df598d08fc77
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: ifsk.rxpdereferenceandfinalizenetfcb, RxpDereferenceAndFinalizeNetFcb, fcb/RxpDereferenceAndFinalizeNetFcb, RxpDereferenceAndFinalizeNetFcb function [Installable File System Drivers], rxref_474f30d3-858e-4179-8236-3068a2325818.xml
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: function
req.header: fcb.h
req.include-header: Fcb.h
req.target-type: Desktop
req.target-min-winverclnt: The RxpDereferenceAndFinalizeNetFcb routine is only available on Windows Server 2003 Service Pack 1 (SP1) and later.
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
-	RxpDereferenceAndFinalizeNetFcb
product: Windows
targetos: Windows
req.typenames: "*PFA_ENTRY, FA_ENTRY"
---

# RxpDereferenceAndFinalizeNetFcb function


## -description


<b>RxpDereferenceAndFinalizeNetFcb</b> decrements the reference count and finalizes an FCB structure.


## -syntax


````
BOOLEAN RxpDereferenceAndFinalizeNetFcb(
  _Out_ PFCB        Fcb,
  _In_  PRX_CONTEXT RxContext,
  _In_  BOOLEAN     RecursiveFinalize,
  _In_  BOOLEAN     ForceFinalize
);
````


## -parameters




### -param ThisFcb

TBD


### -param RxContext [in]

A pointer to the RX_CONTEXT structure associated with the <i>Fcb</i> parameter.


### -param RecursiveFinalize [in]

A parameter that indicates if this should be a recursive finalize operation.


### -param ForceFinalize [in]

A parameter that indicates if this routine should force the <i>Fcb</i> parameter to be finalized.


#### - Fcb [out]

A pointer to the FCB structure to be dereferenced and finalized.


## -returns


<b>RxpDereferenceAndFinalizeNetFcb</b> returns <b>TRUE</b> if the FCB was finalized. 



## -remarks


The referencing and dereferencing of FCBs is different from those of the other data structures because of the embedded resource in the FCB. This implies that the caller requires information regarding the status of the FCB (whether it was finalized or not ).To finalize the FCB, two locks need to be held, the NET_ROOT name table lock as well as the FCB resource. <b>RxpDereferenceAndFinalizeNetFcb</b> acquires the additional lock if required to finalize the FCB.

On checked builds, <b>RxpDereferenceAndFinalizeNetFcb</b> causes the system to ASSERT if <i>ForceFinalize</i> is <b>FALSE</b>, if the node type for the structure is not an FCB, or if the FCB was acquired exclusive.



## -see-also

<a href="..\fcb\nf-fcb-rxpreferencenetfcb.md">RxpReferenceNetFcb</a>

<a href="..\fcb\nf-fcb-rxptrackdereference.md">RxpTrackDereference</a>

<a href="..\fcb\nf-fcb-rxptrackreference.md">RxpTrackReference</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20RxpDereferenceAndFinalizeNetFcb function%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

