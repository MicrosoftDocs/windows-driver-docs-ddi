---
UID: NF:ntifs.CcCanIWrite
title: CcCanIWrite function (ntifs.h)
description: Learn more about the CcCanIWrite function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["CcCanIWrite function"]
ms.keywords: CcCanIWrite, CcCanIWrite routine [Installable File System Drivers], ccref_b964dbf1-d1ad-4929-ab9c-21b1e6f69077.xml, ifsk.cccaniwrite, ntifs/CcCanIWrite
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
 - CcCanIWrite
 - ntifs/CcCanIWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcCanIWrite
---

# CcCanIWrite function

## -description

The **CcCanIWrite** routine determines whether the caller can write to a cached file.

## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file.

### -param BytesToWrite [in]

Number of bytes to be written.

### -param Wait [in]

Set to TRUE if the caller can be put into a wait state until it can write to the cached file, FALSE otherwise.

### -param Retrying [in]

Set to FALSE if this is the first time **CcCanIWrite** is being called for this write request, TRUE otherwise.

## -returns

**CcCanIWrite** returns TRUE if the cache manager can accept the write request, FALSE otherwise.

## -remarks

**CcCanIWrite** should be called before calling [**CcCopyWrite**](nf-ntifs-cccopywrite.md) or [**CcFastCopyWrite**](nf-ntifs-ccfastcopywrite.md).

If **CcCanIWrite** returns TRUE, the caller can immediately call [**CcCopyWrite**](nf-ntifs-cccopywrite.md) or [**CcFastCopyWrite**](nf-ntifs-ccfastcopywrite.md).

If **CcCanIWrite** returns FALSE, the caller must instead call [**CcDeferWrite**](nf-ntifs-ccdeferwrite.md) to defer the write request.

Generally speaking, the cache manager can accept a write request if the following conditions are true:

* The amount of data to be written is not too large.

* There is enough memory to perform the write operation.

* The number of dirty pages in the system cache does not exceed the dirty page threshold (CcDirtyPageThreshold).

* If a per-file dirty page threshold exists for this file, it is not exceeded by the number of dirty pages for this file in the system cache.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

## -see-also

[**CcCopyWrite**](nf-ntifs-cccopywrite.md)

[**CcDeferWrite**](nf-ntifs-ccdeferwrite.md)

[**CcFastCopyWrite**](nf-ntifs-ccfastcopywrite.md)

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**CcSetDirtyPageThreshold**](nf-ntifs-ccsetdirtypagethreshold.md)
