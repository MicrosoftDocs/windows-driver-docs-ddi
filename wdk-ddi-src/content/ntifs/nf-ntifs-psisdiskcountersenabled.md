---
UID: NF:ntifs.PsIsDiskCountersEnabled
title: PsIsDiskCountersEnabled function (ntifs.h)
description: The enabled state of the per process disk I/O counters is returned by the PsIsDiskCountersEnabled routine.
old-location: ifsk\psisdiskcountersenabled.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["PsIsDiskCountersEnabled function"]
ms.keywords: PsIsDiskCountersEnabled, PsIsDiskCountersEnabled routine [Installable File System Drivers], ifsk.psisdiskcountersenabled, ntifs/PsIsDiskCountersEnabled
req.header: ntifs.h
req.include-header: Ntifs.h
req.target-type: Universal
req.target-min-winverclnt: Available starting with Windows 8.
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
req.irql: Any
targetos: Windows
req.typenames: 
f1_keywords:
 - PsIsDiskCountersEnabled
 - ntifs/PsIsDiskCountersEnabled
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - PsIsDiskCountersEnabled
---

# PsIsDiskCountersEnabled function


## -description

The enabled state of the per process disk I/O counters is returned by the <b>PsIsDiskCountersEnabled</b> routine.

## -returns

If TRUE, the disk

## -remarks

A file system driver uses the <b>PsIsDiskCountersEnabled</b> routine to query the system enabled  state of the disk I/O  counters. A file system driver will use this routine prior to accounting for process disk I/O using <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psupdatediskcounters">PsUpdateDiskCounters</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-psupdatediskcounters">PsUpdateDiskCounters</a>
