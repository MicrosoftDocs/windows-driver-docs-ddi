---
UID: NF:fltkernel.FltInitializeOplock
title: FltInitializeOplock function
author: windows-driver-content
description: The FltInitializeOplock routine initializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fltinitializeoplock.htm
old-project: ifsk
ms.assetid: 9878f614-89dc-4b23-8095-2a8c2b80c79d
ms.author: windowsdriverdev
ms.date: 1/9/2018
ms.keywords: fltkernel/FltInitializeOplock, FltInitializeOplock routine [Installable File System Drivers], FltApiRef_e_to_o_5d9b6a6a-6721-41b4-961c-49904596c916.xml, ifsk.fltinitializeoplock, FltInitializeOplock
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
req.irql: "<= APC_LEVEL"
topictype:
-	APIRef
-	kbSyntax
apitype:
-	DllExport
apilocation:
-	fltmgr.sys
apiname:
-	FltInitializeOplock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltInitializeOplock function


## -description


The <b>FltInitializeOplock</b> routine initializes an opportunistic lock (oplock) pointer. 


## -syntax


````
VOID FltInitializeOplock(
  _Out_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [out]

Caller-supplied pointer variable that receives the initialized opaque oplock pointer. This variable must be initialized to <b>NULL</b> before the initial call to <b>FltInitializeOplock</b>. 


## -returns


None 



## -remarks


When the oplock pointer is no longer needed, it can be uninitialized by calling <a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>. The uninitialized oplock pointer can then be initialized for reuse by calling <b>FltInitializeOplock</b>. 

To request an oplock or respond to an oplock break notification, call <a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 



## -see-also

<a href="..\fltkernel\nf-fltkernel-fltuninitializeoplock.md">FltUninitializeOplock</a>

<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>

<a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a>

<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock.md">FsRtlInitializeOplock</a>

<a href="..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md">FltOplockIsFastIoPossible</a>

<a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltInitializeOplock routine%20 RELEASE:%20(1/9/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

