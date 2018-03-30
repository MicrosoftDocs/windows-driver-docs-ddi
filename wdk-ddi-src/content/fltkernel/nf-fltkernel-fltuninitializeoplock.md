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
ms.keywords: FltApiRef_p_to_z_d759e280-7507-44ae-8155-578320562c8b.xml, FltUninitializeOplock, FltUninitializeOplock function [Installable File System Drivers], fltkernel/FltUninitializeOplock, ifsk.fltuninitializeoplock
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	DllExport
api_location:
-	fltmgr.sys
api_name:
-	FltUninitializeOplock
product: Windows
targetos: Windows
req.typenames: EXpsFontRestriction
---

# FltUninitializeOplock function


## -description


<b>FltUninitializeOplock</b> uninitializes an opportunistic lock (oplock) pointer. 


## -parameters




### -param Oplock [in]

Opaque oplock pointer. This pointer must have been initialized by a previous call to <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>. 


## -returns



None 




## -remarks



Minifilter drivers call <b>FltUninitializeOplock</b> to uninitialize an initialized opportunistic lock (oplock) pointer. The uninitialized oplock pointer can be initialized for reuse by calling <a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff545462">FSCTL_OPBATCH_ACK_CLOSE_PENDING</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545468">FSCTL_OPLOCK_BREAK_ACKNOWLEDGE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545476">FSCTL_OPLOCK_BREAK_ACK_NO_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545485">FSCTL_OPLOCK_BREAK_NOTIFY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545510">FSCTL_REQUEST_BATCH_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545518">FSCTL_REQUEST_FILTER_OPLOCK</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545538">FSCTL_REQUEST_OPLOCK_LEVEL_1</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff545546">FSCTL_REQUEST_OPLOCK_LEVEL_2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541844">FltCheckOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541946">FltCurrentBatchOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543289">FltInitializeOplock</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543398">FltOplockFsctrl</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff543404">FltOplockIsFastIoPossible</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547328">FsRtlUninitializeOplock</a>
 

 

