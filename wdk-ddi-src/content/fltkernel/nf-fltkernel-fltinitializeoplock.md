---
UID: NF:fltkernel.FltInitializeOplock
title: FltInitializeOplock function (fltkernel.h)
description: The FltInitializeOplock routine initializes an opportunistic lock (oplock) pointer.
old-location: ifsk\fltinitializeoplock.htm
tech.root: ifsk
ms.assetid: 9878f614-89dc-4b23-8095-2a8c2b80c79d
ms.date: 04/16/2018
ms.keywords: FltApiRef_e_to_o_5d9b6a6a-6721-41b4-961c-49904596c916.xml, FltInitializeOplock, FltInitializeOplock routine [Installable File System Drivers], fltkernel/FltInitializeOplock, ifsk.fltinitializeoplock
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
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltInitializeOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltInitializeOplock function


## -description


The <b>FltInitializeOplock</b> routine initializes an opportunistic lock (oplock) pointer. 


## -parameters




### -param Oplock [out]

Caller-supplied pointer variable that receives the initialized opaque oplock pointer. This variable must be initialized to <b>NULL</b> before the initial call to <b>FltInitializeOplock</b>. 


## -returns



None 




## -remarks



When the oplock pointer is no longer needed, it can be uninitialized by calling <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuninitializeoplock">FltUninitializeOplock</a>. The uninitialized oplock pointer can then be initialized for reuse by calling <b>FltInitializeOplock</b>. 

To request an oplock or respond to an oplock break notification, call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockfsctrl">FltOplockFsctrl</a>. 

For detailed information about opportunistic locks, see the Microsoft Windows SDK documentation. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcheckoplock">FltCheckOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltcurrentbatchoplock">FltCurrentBatchOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockfsctrl">FltOplockFsctrl</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltoplockisfastiopossible">FltOplockIsFastIoPossible</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/fltkernel/nf-fltkernel-fltuninitializeoplock">FltUninitializeOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>
 

 

