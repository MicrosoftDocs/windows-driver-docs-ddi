---
UID: NF:ntifs.CcScheduleReadAhead
title: CcScheduleReadAhead function (ntifs.h)
description: The CcScheduleReadAhead routine performs read-ahead (also called &#0034;lazy read&#0034;) on a cached file. CcScheduleReadAhead should never be called directly. The CcReadAhead macro should be called instead.
old-location: ifsk\ccschedulereadahead.htm
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["CcScheduleReadAhead function"]
ms.keywords: CcScheduleReadAhead, CcScheduleReadAhead routine [Installable File System Drivers], ccref_ae4b3e52-9f23-499f-86f1-81e813484007.xml, ifsk.ccschedulereadahead, ntifs/CcScheduleReadAhead
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
 - CcScheduleReadAhead
 - ntifs/CcScheduleReadAhead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcScheduleReadAhead
---

# CcScheduleReadAhead function


## -description

The <b>CcScheduleReadAhead</b> routine performs read-ahead (also called "lazy read") on a cached file. <b>CcScheduleReadAhead</b> should never be called directly. The <b>CcReadAhead</b> macro should be called instead.

## -parameters

### -param FileObject [in]


Pointer to a file object for the file on which read-ahead is to be performed.

### -param FileOffset [in]


Pointer to a variable that specifies the starting byte offset within the cached file where the last read occurred.

### -param Length [in]


Length in bytes of the range that was last read.

## -remarks

The <b>CcReadAhead</b> macro is a wrapper for <b>CcScheduleReadAhead</b>. It calls <b>CcScheduleReadAhead</b> only if <i>Length</i> >= 256. Measurements have shown that calling <b>CcScheduleReadAhead</b> for smaller reads actually decreases performance.

<b>CcReadAhead</b> and <b>CcScheduleReadAhead</b> can only be called after a successful call to <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopyread">CcCopyRead</a>, <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccfastcopyread">CcFastCopyRead</a>, or <a href="/previous-versions/ff539159(v=vs.85)">CcMdlRead</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-cccopyread">CcCopyRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccfastcopyread">CcFastCopyRead</a>



<a href="/previous-versions/ff539159(v=vs.85)">CcMdlRead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccschedulereadahead">CcScheduleReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetreadaheadgranularity">CcSetReadAheadGranularity</a>
