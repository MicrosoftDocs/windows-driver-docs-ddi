---
UID: NF:ntifs.CcCopyReadEx
title: CcCopyReadEx function (ntifs.h)
description: Learn more about the CcCopyReadEx routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["CcCopyReadEx function"]
ms.keywords: CcCopyReadEx, ifsk.cccopyreadex, ntifs/CcCopyReadEx
req.header: ntifs.h
req.include-header: Ntifs.h, FltKernel.h
req.target-type: Universal
req.target-min-winverclnt: Windows 8
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
 - CcCopyReadEx
 - ntifs/CcCopyReadEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcCopyReadEx
---

# CcCopyReadEx function

## -description

The **CcCopyReadEx** routine copies data from a cached file to a user buffer. The I/O byte count for the operation is charged to the issuing thread.

## -parameters

### -param FileObject [in]

A pointer to a file object for the cached file from which the data is to be read.

### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file.

### -param Length [in]

The length in bytes of the data to be read.

### -param Wait [in]

Set to TRUE if the caller can be put into a wait state until all the data has been copied, FALSE otherwise.

### -param Buffer [out]

A pointer to a buffer into which the data is to be copied.

### -param IoStatus [out]

A pointer to a caller-allocated structure that receives the final completion status and information about the operation. If not all of the data is copied successfully, **IoStatus.Information** contains the actual number of bytes that were copied.

### -param IoIssuerThread [in]

The thread issuing the read request. For a file system with disk I/O accounting enabled, this is the thread the I/O is charged to. If **IoIssuerThread** is NULL, the I/O is charged to the current thread.

## -returns

The **CcCopyReadEx** routine returns TRUE if the data was copied successfully, FALSE otherwise.

## -remarks

If **Wait** is TRUE, **CcCopyReadEx** is guaranteed to complete the copy request and return TRUE. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If **Wait** is FALSE, **CcCopyReadEx** will refuse to block, and will return FALSE, if the required pages of the cached file are not already resident in memory.

**FileOffset** plus **Length** must be less than or equal to the size of the cached file, or an assertion failure will occur.

If any failure occurs, **CcCopyReadEx** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcCopyReadEx** raises an exception with the **STATUS_INSUFFICIENT_RESOURCES** status; if an I/O error occurs, **CcCopyReadEx** raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcCopyReadEx** in a **try-except** or **try-finally** statement.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

## -see-also

[**CcFastCopyRead**](nf-ntifs-ccfastcopyread.md)

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**CcReadAhead**](/previous-versions/ff539191(v=vs.85))

[**CcScheduleReadAhead**](nf-ntifs-ccschedulereadahead.md)

[**CcSetAdditionalCacheAttributes**](nf-ntifs-ccsetadditionalcacheattributes.md)

[**CcSetReadAheadGranularity**](nf-ntifs-ccsetreadaheadgranularity.md)
