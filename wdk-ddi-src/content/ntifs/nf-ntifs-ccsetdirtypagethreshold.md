---
UID: NF:ntifs.CcSetDirtyPageThreshold
title: CcSetDirtyPageThreshold function (ntifs.h)
description: The CcSetDirtyPageThreshold routine sets a per-file dirty page threshold on a cached file.
old-location: ifsk\ccsetdirtypagethreshold.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcSetDirtyPageThreshold function"]
ms.keywords: CcSetDirtyPageThreshold, CcSetDirtyPageThreshold routine [Installable File System Drivers], ccref_df331e54-32a2-4a09-a1e6-7c1d69b2abcf.xml, ifsk.ccsetdirtypagethreshold, ntifs/CcSetDirtyPageThreshold
req.header: ntifs.h
req.include-header: Ntifs.h
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
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: 
targetos: Windows
req.typenames: 
f1_keywords:
 - CcSetDirtyPageThreshold
 - ntifs/CcSetDirtyPageThreshold
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetDirtyPageThreshold
---

# CcSetDirtyPageThreshold function


## -description

The <b>CcSetDirtyPageThreshold</b> routine sets a per-file dirty page threshold on a cached file.

## -parameters

### -param FileObject [in]


Pointer to a file object for the cached file on which the dirty page threshold is to be set.

### -param DirtyPageThreshold [in]


Specifies, as a number of pages, the dirty page threshold value. To remove a per-file dirty page threshold value that was set previously, set <i>DirtyPageThreshold</i> to zero.

## -remarks

<b>CcSetDirtyPageThreshold</b> sets or removes a per-file dirty page threshold. After a per-file dirty page threshold is set on a cached file, if the file system attempts to exceed the threshold, the cache manager will refuse requests to write to the file.

To determine whether the cache manager will accept or refuse write requests, use <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccaniwrite">CcCanIWrite</a>.

Note that the <i>per-file</i> dirty page threshold is not the same as the <i>global</i> dirty page threshold for the entire system cache.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccaniwrite">CcCanIWrite</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccdeferwrite">CcDeferWrite</a>
