---
UID: NF:ntifs.FsRtlCurrentOplockH
title: FsRtlCurrentOplockH function (ntifs.h)
description: A file system or filter driver calls FsRtlCurrentOplockH to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file.
old-location: ifsk\fsrtlcurrentoplockh.htm
tech.root: ifsk
ms.assetid: 98eb2bef-18ac-449f-b180-7b0f768cc093
ms.date: 04/16/2018
keywords: ["FsRtlCurrentOplockH function"]
ms.keywords: FsRtlCurrentOplockH, FsRtlCurrentOplockH function [Installable File System Drivers], fsrtlref_4997ca62-379d-45d8-bc22-32efd2076692.xml, ifsk.fsrtlcurrentoplockh, ntifs/FsRtlCurrentOplockH
f1_keywords:
 - "ntifs/FsRtlCurrentOplockH"
 - "FsRtlCurrentOplockH"
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: The FsRtlCurrentOplockH routine is available starting with Windows 7.
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
- FsRtlCurrentOplockH
targetos: Windows
req.typenames: 
---

# FsRtlCurrentOplockH function


## -description


A file system or filter driver calls <b>FsRtlCurrentOplockH</b> to determine whether there are any CACHE_HANDLE_LEVEL opportunistic locks (oplocks) on a file. 


## -parameters




### -param Oplock 
[in]
An opaque opportunistic lock pointer for the file. This pointer must have been initialized by a previous call to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>. 


## -returns



<b>FsRtlCurrentOplockH</b> returns <b>TRUE</b> if there are CACHE_HANDLE_LEVEL opportunistic locks that are currently being held. Otherwise, it returns <b>FALSE</b>. 




## -remarks



<b>FsRtlCurrentOplockH</b> returns <b>FALSE</b> if no CACHE_HANDLE_LEVEL opportunistic locks (oplocks) are currently held.

For more information about opportunistic locks, see the Microsoft Windows SDK documentation. 

Minifilters should call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentoplockh">FltCurrentOplockH</a> instead of <b>FsRtlCurrentOplock</b>. 




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltcurrentoplockh">FltCurrentOplockH</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializeoplock">FsRtlInitializeOplock</a>
 

 

