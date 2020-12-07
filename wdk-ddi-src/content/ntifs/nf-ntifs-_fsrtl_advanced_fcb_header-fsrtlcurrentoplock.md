---
UID: NF:ntifs.FsRtlCurrentOplock
title: FsRtlCurrentOplock function (ntifs.h)
description: A file system or filter driver calls FsRtlCurrentOplock to determine whether there are any opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentoplock.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlCurrentOplock function"]
ms.keywords: FsRtlCurrentOplock, FsRtlCurrentOplock function [Installable File System Drivers], fsrtlref_3caa67c9-324a-4694-95a3-f84105055b48.xml, ifsk.fsrtlcurrentoplock, ntifs/FsRtlCurrentOplock
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FsRtlCurrentOplock
 - ntifs/FsRtlCurrentOplock
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlCurrentOplock
---

# FsRtlCurrentOplock function


## -description

A file system or filter driver calls <b>FsRtlCurrentOplock</b> to determine whether there are any opportunistic locks (oplocks) on a file.

## -parameters

### -param Oplock 

[in]
An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>.

## -returns

<b>FsRtlCurrentOplock</b> returns <b>TRUE</b> if there are opportunistic locks (oplocks) that are currently being held. Otherwise, it returns <b>FALSE</b>.

## -remarks

<b>FsRtlCurrentOplock</b> returns <b>FALSE</b> if no opportunistic locks are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentoplock">FltCurrentOplock</a> instead of <b>FsRtlCurrentOplock</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentoplock">FltCurrentOplock</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>
