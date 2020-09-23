---
UID: NF:ntifs.CcSetReadAheadGranularity
title: CcSetReadAheadGranularity function (ntifs.h)
description: The CcSetReadAheadGranularity routine sets the read-ahead granularity for a cached file.
old-location: ifsk\ccsetreadaheadgranularity.htm
tech.root: ifsk
ms.assetid: 3ab0c8b8-1f41-48b7-9c42-ea843ebcd82e
ms.date: 04/16/2018
keywords: ["CcSetReadAheadGranularity function"]
ms.keywords: CcSetReadAheadGranularity, CcSetReadAheadGranularity routine [Installable File System Drivers], ccref_9b995224-0e59-43c6-b827-c15d9ae6e86c.xml, ifsk.ccsetreadaheadgranularity, ntifs/CcSetReadAheadGranularity
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
 - CcSetReadAheadGranularity
 - ntifs/CcSetReadAheadGranularity
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetReadAheadGranularity
---

# CcSetReadAheadGranularity function


## -description

The <b>CcSetReadAheadGranularity</b> routine sets the read-ahead granularity for a cached file.

## -parameters

### -param FileObject 

[in]
Pointer to a file object for the cached file whose read-ahead granularity is to be set.

### -param Granularity 

[in]
Specifies the desired read-ahead granularity, which must be an even power of two and must be greater than or equal to PAGE_SIZE.

## -remarks

After <a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a> is called to cache a file, but before <b>CcSetReadAheadGranularity</b> is called for the cached file, the default read-ahead granularity for the cached file is equal to PAGE_SIZE.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccinitializecachemap">CcInitializeCacheMap</a>



<a href="/previous-versions/ff539191(v=vs.85)">CcReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccschedulereadahead">CcScheduleReadAhead</a>



<a href="/windows-hardware/drivers/ddi/ntifs/nf-ntifs-ccsetadditionalcacheattributes">CcSetAdditionalCacheAttributes</a>