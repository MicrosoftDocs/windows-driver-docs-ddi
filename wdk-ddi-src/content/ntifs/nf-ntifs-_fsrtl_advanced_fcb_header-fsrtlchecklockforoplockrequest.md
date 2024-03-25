---
UID: NF:ntifs.FsRtlCheckLockForOplockRequest
title: FsRtlCheckLockForOplockRequest function (ntifs.h)
description: Learn more about the FsRtlCheckLockForOplockRequest routine.
tech.root: ifsk
ms.date: 07/06/2023
keywords: ["FsRtlCheckLockForOplockRequest function"]
ms.keywords: FsRtlCheckLockForOplockRequest, ifsk.fsrtlchecklockforoplockrequest, ntifs/FsRtlCheckLockForOplockRequest
req.header: ntifs.h
req.include-header: Ntifs.h
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
ms.custom: RS5
f1_keywords:
 - FsRtlCheckLockForOplockRequest
 - ntifs/FsRtlCheckLockForOplockRequest
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlCheckLockForOplockRequest
dev_langs:
 - c++
---

# FsRtlCheckLockForOplockRequest function

## -description

The **FsRtlCheckLockForOplockRequest** routine checks for locks within the allocation size of a file. The file lock object is checked for the presence of byte range locks that would prevent an oplock request from being granted.

## -parameters

### -param FileLock [in]

The file lock that specifies locked ranges.

### -param AllocationSize [in]

The file allocation size to check for any locked ranges.

## -returns

**FsRtlCheckLockForOplockRequest** returns TRUE if the oplock request can be granted; otherwise it returns FALSE.

## -remarks

**FsRtlCheckLockForOplockRequest** returns **TRUE** if **AllocationSize** = 0.

If **FileLock** has any pending lock requests, the check fails and **FsRtlCheckLockForOplockRequest** returns **FALSE**.
