---
UID: NF:ntifs.CcCopyWriteEx
title: CcCopyWriteEx function (ntifs.h)
description: Learn more about the CcCopyWriteEx routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["CcCopyWriteEx function"]
ms.keywords: CcCopyWriteEx, ifsk.cccopywriteex, ntifs/CcCopyWriteEx
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
 - CcCopyWriteEx
 - ntifs/CcCopyWriteEx
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - CcCopyWriteEx
---

# CcCopyWriteEx function

## -description

The **CcCopyWriteEx** routine copies data from a user buffer to a cached file. The I/O byte count for the operation is charged to the issuing thread.

## -parameters

### -param FileObject [in]

A pointer to a file object for the cached file to which the data is to be written.

### -param FileOffset [in]

A pointer to a variable that specifies the starting byte offset within the cached file.

### -param Length [in]

The length in bytes of the data to be written.

### -param Wait [in]

Set to TRUE if the caller can be put into a wait state until all the data has been copied, FALSE otherwise.

### -param Buffer [in]

A pointer to the buffer from which the data is to be copied.

### -param IoIssuerThread [in]

The thread issuing the write request. For a file system with disk I/O accounting enabled, this is the thread the I/O is charged to. If **IoIssuerThread** is NULL, the I/O is charged to the current thread.

## -returns

The **CcCopyWriteEx** routine returns TRUE if the data was copied successfully, FALSE otherwise.

## -remarks

If **Wait** is TRUE, **CcCopyWriteEx** is guaranteed to complete the copy request and return TRUE. If the required pages of the cached file are already resident in memory, the data will be copied immediately and no blocking will occur. If any needed pages are not resident, the caller will be put in a wait state until all required pages have been made resident and the data can be copied.

If **Wait** is FALSE, **CcCopyWriteEx** will refuse to block, and will return FALSE, if the required pages of the cached file are not already resident in memory or if the FO_WRITE_THROUGH flag is set on the file object.

If any failure occurs, **CcCopyWriteEx** raises a status exception for that particular failure. For example, if a pool allocation failure occurs, **CcCopyWriteEx** raises an exception with the **STATUS_INSUFFICIENT_RESOURCES** status; if an I/O error occurs, **CcCopyWriteEx** raises the status exception of the I/O error. Therefore, to gain control if a failure occurs, the driver should wrap the call to **CcCopyWriteEx** in a **try-except** or **try-finally** statement.

To cache a file, use [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)
