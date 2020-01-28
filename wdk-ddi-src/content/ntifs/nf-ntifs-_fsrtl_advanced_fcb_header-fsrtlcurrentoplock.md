---
UID: NF:ntifs.FsRtlCurrentOplock
title: FsRtlCurrentOplock function (ntifs.h)
description: A file system or filter driver calls FsRtlCurrentOplock to determine whether there are any opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentoplock.htm
tech.root: ifsk
ms.assetid: b7cf8765-6f24-4b65-9171-6bfad7214013
ms.date: 04/16/2018
ms.keywords: FsRtlCurrentOplock, FsRtlCurrentOplock function [Installable File System Drivers], fsrtlref_3caa67c9-324a-4694-95a3-f84105055b48.xml, ifsk.fsrtlcurrentoplock, ntifs/FsRtlCurrentOplock
f1_keywords:
 - "ntifs/FsRtlCurrentOplock"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCurrentOplock routine is available starting with Windows Vista.
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- NtosKrnl.exe
api_name:
- FsRtlCurrentOplock
product:
- Windows
targetos: Windows
req.typenames: 
---

# FsRtlCurrentOplock function


## -description


A file system or filter driver calls <b>FsRtlCurrentOplock</b> to determine whether there are any opportunistic locks (oplocks) on a file. 


## -parameters




### -param Oplock [in]

An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


## -returns



<b>FsRtlCurrentOplock</b> returns <b>TRUE</b> if there are opportunistic locks (oplocks) that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FsRtlCurrentOplock</b> returns <b>FALSE</b> if no opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentoplock">FltCurrentOplock</a> instead of <b>FsRtlCurrentOplock</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentoplock">FltCurrentOplock</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>
 

 

