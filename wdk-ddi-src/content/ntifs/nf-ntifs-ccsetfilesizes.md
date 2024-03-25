---
UID: NF:ntifs.CcSetFileSizes
title: CcSetFileSizes function (ntifs.h)
description: Learn more about the CcSetFileSizes function.
tech.root: ifsk
ms.date: 02/02/2024
keywords: ["CcSetFileSizes function"]
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
 - CcSetFileSizes
 - ntifs/CcSetFileSizes
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcSetFileSizes
---

# CcSetFileSizes function

## -description

The **CcSetFileSizes** routine updates the cache maps and section object for a cached file whose size has changed. Use [**CcSetFileSizesEx**](nf-ntifs-ccsetfilesizesex.md) instead since it provides an NTSTATUS return code along with better guidance for error handling.

## -parameters

### -param FileObject [in]

Pointer to a file object for the cached file.

### -param FileSizes [in]

Pointer to a [**CC_FILE_SIZES**](ns-ntifs-cc_file_sizes.md) structure containing the new file size information.

## -remarks

File systems must call [**CcSetFileSizesEx**](nf-ntifs-ccsetfilesizesex.md) or **CcSetFileSizes** to update the cache manager data structures whenever one of the following changes is made to a cached file:

* Its allocation size is increased.

* Its valid data length is decreased.

* Its valid data length is increased by a non-cached I/O operation.

* Its file size is increased or decreased.

If any failure occurs, **CcSetFileSizes** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcSetFileSizes** raises a STATUS_INSUFFICIENT_RESOURCES exception. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcSetFileSizes** in a *try-except* or *try-finally* statement.

The file system must ensure that the cache map is valid and will remain so for the duration of this call.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

To get the size of the cached file, pass **FileObject** to [**CcGetFileSizePointer**](nf-ntifs-ccgetfilesizepointer.md).

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

 [**CcSetFileSizesEx**](nf-ntifs-ccsetfilesizesex.md)
