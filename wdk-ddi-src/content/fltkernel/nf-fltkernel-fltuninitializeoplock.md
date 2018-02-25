---
UID: NF:fltkernel.FltUninitializeOplock
title: FltUninitializeOplock function
author: windows-driver-content
description: FltUninitializeOplock uninitializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fltuninitializeoplock.htm
old-project: ifsk
ms.assetid: 6379014a-f9bc-4e86-93da-83d90f009a3b
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: ",  , F, FltApiRef_p_to_z_d759e280-7507-44ae-8155-578320562c8b.xml, FltUninitializeOplock, FltUninitializeOplock function [Installable File System Drivers], O, U, a, c, e, fltkernel/FltUninitializeOplock, i, ifsk.fltuninitializeoplock, k, l, n, o, p, t, z"
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
-	FltUninitializeOplock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltUninitializeOplock function


## -description


<b>FltUninitializeOplock</b> uninitializes an opportunistic lock (oplock) pointer. 


## -syntax


````
VOID FltUninitializeOplock(
  _In_ POPLOCK Oplock
);
````


## -parameters




### -param Oplock [in]

Opaque oplock pointer. This pointer must have been initialized by a previous call to <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. 


## -returns



None 




## -remarks



Minifilter drivers call <b>FltUninitializeOplock</b> to uninitialize an initialized opportunistic lock (oplock) pointer. The uninitialized oplock pointer can be initialized for reuse by calling <a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="..\ntifs\nf-ntifs-_fsrtl_advanced_fcb_header-fsrtluninitializeoplock.md">FsRtlUninitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="..\fltkernel\nf-fltkernel-fltinitializeoplock.md">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="..\fltkernel\nf-fltkernel-fltcurrentbatchoplock.md">FltCurrentBatchOplock</a>



<a href="..\fltkernel\nf-fltkernel-fltoplockisfastiopossible.md">FltOplockIsFastIoPossible</a>



<a href="..\fltkernel\nf-fltkernel-fltcheckoplock.md">FltCheckOplock</a>



<a href="..\fltkernel\nf-fltkernel-fltoplockfsctrl.md">FltOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [ifsk\ifsk]:%20FltUninitializeOplock function%20 RELEASE:%20(2/16/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

