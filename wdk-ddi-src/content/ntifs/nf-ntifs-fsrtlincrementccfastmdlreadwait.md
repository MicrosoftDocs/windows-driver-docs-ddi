---
UID: NF:ntifs.FsRtlIncrementCcFastMdlReadWait
title: FsRtlIncrementCcFastMdlReadWait function (ntifs.h)
description: The FsRtlIncrementCcFastMdlReadWait routine increments the cache manager's CcFastMdlReadWait performance counter member in a processor control block (PRCB) object.
old-location: ifsk\fsrtlincrementccfastmdlreadwait.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlIncrementCcFastMdlReadWait function"]
ms.keywords: FsRtlIncrementCcFastMdlReadWait, FsRtlIncrementCcFastMdlReadWait routine [Installable File System Drivers], fsrtlref_6ab13976-a131-41bf-970c-f2a554d87d92.xml, ifsk.fsrtlincrementccfastmdlreadwait, ntifs/FsRtlIncrementCcFastMdlReadWait
req.header: ntifs.h
req.include-header: FltKernel.h, Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Windows Vista
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
 - FsRtlIncrementCcFastMdlReadWait
 - ntifs/FsRtlIncrementCcFastMdlReadWait
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlIncrementCcFastMdlReadWait
---

# FsRtlIncrementCcFastMdlReadWait function


## -description

The <b>FsRtlIncrementCcFastMdlReadWait </b>routine increments the cache manager's <b>CcFastMdlReadWait</b> performance counter member in a processor control block (<a href="/windows-hardware/drivers/">PRCB</a>) object.

## -remarks

<b>FsRtlIncrementCcFastMdlReadWait </b>increments the cache manager's <b>CcFastMdlReadWait</b> performance counter in the per-processor control block for the processor on which <b>FsRtlIncrementCcFastMdlReadWait</b> is called. This counter records the number of fast I/O <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a> read operations (FsRtlMdlRead) serviced by a file system driver.  

File system drivers should call this function to update the <b>CcFastMdlReadWait</b> performance counter if the driver chooses to override the default fast I/O MDL read handler.

The counter is only used to record fast I/O MDL read operations for a nonzero length.  <b>FsRtlIncrementCcFastMdlReadWait</b> should not be called for a zero-length fast I/O MDL read.

File system drivers should not increment the <b>CcFastMdlReadWait</b> performance counter if their fast I/O MDL read handler returns <b>FALSE</b> due to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a> returning a non-<b>NULL</b> value.  The counter should only be incremented if the file system driver actually attempts to satisfy a nonzero-length fast I/O MDL read.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_mdl">MDL</a>
