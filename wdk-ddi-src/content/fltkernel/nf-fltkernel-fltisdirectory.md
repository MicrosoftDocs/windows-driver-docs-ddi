---
UID: NF:fltkernel.FltIsDirectory
title: FltIsDirectory function (fltkernel.h)
description: A minifilter driver calls the FltIsDirectory routine to determine whether a given file object represents a directory.
old-location: ifsk\fltisdirectory.htm
tech.root: ifsk
ms.assetid: a9343e09-0b7b-4ed8-9b30-63ee0b38d13d
ms.date: 04/16/2018
keywords: ["FltIsDirectory function"]
ms.keywords: FltApiRef_e_to_o_cdcea60b-c299-4445-9c96-126210f2a43e.xml, FltIsDirectory, FltIsDirectory routine [Installable File System Drivers], fltkernel/FltIsDirectory, ifsk.fltisdirectory
req.header: fltkernel.h
req.include-header: FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available on Microsoft Windows 2000 Update Rollup 1 for SP4, Windows XP SP2, Microsoft Windows Server 2003 SP1, and later.  Note that this routine is not available on Windows 2000 SP4 or earlier.
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
req.lib: Fltmgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - FltIsDirectory
 - fltkernel/FltIsDirectory
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltIsDirectory
---

# FltIsDirectory function


## -description

A minifilter driver calls the <b>FltIsDirectory</b> routine to determine whether a given file object represents a directory.

## -parameters

### -param FileObject 

[in]
Pointer to an already opened file object.

### -param Instance 

[in]
Opaque instance pointer for the instance associated with this file object.

### -param IsDirectory 

[out]
Pointer to a caller-supplied Boolean variable. On return, this variable receives <b>TRUE</b> if the file object represents a directory, <b>FALSE</b> otherwise.

## -returns

<b>FltIsDirectory</b> returns STATUS_SUCCESS or an appropriate NTSTATUS value, such as the following: 

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_NOT_SUPPORTED</b></dt>
</dl>
</td>
<td width="60%">
This error code is returned if the file system does not support stream contexts.  Note that starting with Windows Vista, <a href="/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltisdirectory">FltIsDirectory</a> will return directory information even for file systems that do not support stream contexts.  

</td>
</tr>
</table>

## -remarks

<b>FltIsDirectory</b> retrieves the desired information from the filter manager's internal stream context manager. The filter manager caches this information for future queries on this stream.

<div class="alert"><b>Note</b>  This routine can only be called on an opened file object.</div>
<div> </div>

## -see-also

<a href="/previous-versions/ff547285(v=vs.85)">FsRtlSupportsPerStreamContexts</a>