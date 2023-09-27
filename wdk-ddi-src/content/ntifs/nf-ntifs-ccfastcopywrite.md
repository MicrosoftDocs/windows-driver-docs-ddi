---
UID: NF:ntifs.CcFastCopyWrite
title: CcFastCopyWrite function (ntifs.h)
description: Learn more about the CcFastCopyWrite function.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["CcFastCopyWrite function"]
ms.keywords: CcFastCopyWrite, CcFastCopyWrite routine [Installable File System Drivers], ccref_f5763242-c6f6-4638-8577-a6c65001a8ca.xml, ifsk.ccfastcopywrite, ntifs/CcFastCopyWrite
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
 - CcFastCopyWrite
 - ntifs/CcFastCopyWrite
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcFastCopyWrite
---

# CcFastCopyWrite function

## -description

The **CcFastCopyWrite** routine performs a fast copy write from a buffer in memory to a cached file.

## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file to which the data is to be written.

### -param FileOffset [in]

Pointer to a variable that specifies the starting byte offset within the cached file.

### -param Length [in]

Length in bytes of the data to be written.

### -param Buffer [in]

Pointer to the buffer from which the data is to be copied.

## -remarks

**CcFastCopyWrite** is a faster version of [**CcCopyWrite**](nf-ntifs-cccopywrite.md). It differs from **CcCopyWrite** in the following respects:

* **FileOffset** is a ULONG, not a PLARGE_INTEGER.

* There is no **Wait** parameter. The caller must be able to enter a wait state until all the data has been copied.

* **CcFastCopyWrite** does not return a BOOLEAN to indicate whether the write operation was successful.

If the required pages of the cached file are already resident in memory, the data is copied immediately and no blocking occurs. If any needed pages are not resident, the caller is put in a wait state until all required pages have been made resident and the data can be copied.

If any failure occurs, **CcFastCopyWrite** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcFastCopyWrite** raises a STATUS_INSUFFICIENT_RESOURCES exception; if an I/O error occurs, **CcFastCopyWrite** raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcFastCopyWrite** in a *try-except* or *try-finally* statement.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

## -see-also

[**CcCopyWrite**](nf-ntifs-cccopywrite.md)

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)
