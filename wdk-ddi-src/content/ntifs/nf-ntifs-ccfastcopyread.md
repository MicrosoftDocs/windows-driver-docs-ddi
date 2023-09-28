---
UID: NF:ntifs.CcFastCopyRead
title: CcFastCopyRead function (ntifs.h)
description: Learn more about the CcFastCopyRead function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["CcFastCopyRead function"]
ms.keywords: CcFastCopyRead, CcFastCopyRead routine [Installable File System Drivers], ccref_7198ef60-5199-4597-9809-ddacc59e6223.xml, ifsk.ccfastcopyread, ntifs/CcFastCopyRead
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
req.irql: < DISPATCH_LEVEL
targetos: Windows
req.typenames: 
f1_keywords:
 - CcFastCopyRead
 - ntifs/CcFastCopyRead
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcFastCopyRead
---

# CcFastCopyRead function

## -description

The **CcFastCopyRead** routine performs a fast copy read from a cached file to a buffer in memory.

## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file from which the data is to be read.

### -param FileOffset [in]

Starting byte offset within the cached file.

### -param Length [in]

Length in bytes of the data to be read.

### -param PageCount [in]

Number of pages spanned by the read.

### -param Buffer [out]

Pointer to a buffer into which the data is to be copied.

### -param IoStatus [out]

Pointer to a structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, **IoStatus.Information** contains the actual number of bytes that were copied.

## -remarks

**CcFastCopyRead** is a faster version of [**CcCopyRead**](nf-ntifs-cccopyread.md). It differs from **CcCopyRead** in the following respects:

* **FileOffset** is a ULONG, not a PLARGE_INTEGER.

* There is no **Wait** parameter. The caller must be able to enter a wait state until all the data has been copied.

* **CcFastCopyRead** does not return a BOOLEAN to indicate whether the read operation was successful.

**FileOffset** plus **Length** must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, **CcFastCopyRead** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcFastCopyRead** raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, **CcFastCopyRead** raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcFastCopyRead** in a *try-except* or *try-finally* statement.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

## -see-also

[**CcCopyRead**](nf-ntifs-cccopyread.md)

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**CcReadAhead**](/previous-versions/ff539191(v=vs.85))

[**CcScheduleReadAhead**](nf-ntifs-ccschedulereadahead.md)

[**CcSetAdditionalCacheAttributes**](nf-ntifs-ccsetadditionalcacheattributes.md)

[**CcSetReadAheadGranularity**](nf-ntifs-ccsetreadaheadgranularity.md)
