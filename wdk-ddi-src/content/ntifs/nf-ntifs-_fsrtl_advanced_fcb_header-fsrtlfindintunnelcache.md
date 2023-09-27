---
UID: NF:ntifs.FsRtlFindInTunnelCache
title: FsRtlFindInTunnelCache function (ntifs.h)
description: Learn more about the FsRtlFindInTunnelCache function.
tech.root: ifsk
ms.date: 04/16/2018
keywords: ["FsRtlFindInTunnelCache function"]
ms.keywords: FsRtlFindInTunnelCache, FsRtlFindInTunnelCache routine [Installable File System Drivers], fsrtlref_ae11e9b8-bc4f-4c56-84a7-8e328e215415.xml, ifsk.fsrtlfindintunnelcache, ntifs/FsRtlFindInTunnelCache
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
req.irql: <= APC_LEVEL
targetos: Windows
req.typenames: 
ms.custom: RS5
f1_keywords:
 - FsRtlFindInTunnelCache
 - ntifs/FsRtlFindInTunnelCache
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - FsRtlFindInTunnelCache
dev_langs:
 - c++
---

# FsRtlFindInTunnelCache function

## -description

The **FsRtlFindInTunnelCache** routine searches for a matching entry in the tunnel cache that matches the specified name.

## -parameters

### -param Cache [in]

Pointer to a tunnel cache initialized by [**FsRtlInitializeTunnelCache**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md).

### -param DirectoryKey

Key value of the directory containing the file that is being created or renamed.

### -param Name [in]

Pointer to a Unicode string containing the new name for the file that is being renamed or created.

### -param ShortName [out]

Pointer to a caller-allocated Unicode string to receive the short name of the tunneled file. This string must be long enough to hold a full 8.3 file name. (Unlike **LongName**, **ShortName** is not grown dynamically.)

### -param LongName [out]

Pointer to a caller-allocated Unicode string to receive the long name of the tunneled file. If this string is not large enough to hold the tunneled name, **FsRtlFindInTunnelCache** replaces it with a larger system-allocated string. If such a string is allocated, the caller is responsible for detecting this case and freeing the new system-allocated string as well as the original caller-allocated string.

### -param DataLength [in, out]

On input, this is a pointer to a variable that specifies the length of the buffer pointed to by **Data**. On output, the same variable receives the length in bytes of the data written to the buffer.

### -param Data [out]

Pointer to a caller-allocated buffer to receive the data found in the tunnel cache.

## -returns

**FsRtlFindInTunnelCache** returns TRUE if a matching entry is found in the tunnel cache, FALSE otherwise.

## -remarks

File systems can call **FsRtlFindInTunnelCache** when a file name is added to a directory for a file that is being created or renamed. **FsRtlFindInTunnelCache** searches the tunnel cache for an entry that matches **DirKey** and **Name**. If one is found, **FsRtlFindInTunnelCache** fetches the cached information.

The match is performed as follows:

* The value of **DirKey** is compared against the entry's directory key. (This is the **DirectoryKey** value that was passed to **FsRtlAddToTunnelCache**.)

* If **KeyByShortName** was set to TRUE in the call to **FsRtlAddToTunnelCache**, the string pointed to by **Name** is compared against the short name of the tunneled file. Otherwise, it is compared against the long name.

The value of the buffer length variable pointed to by **DataLength** must be greater than or equal to the length in bytes of the data stored in the tunnel cache entry.

The caller is required to synchronize this call against [**FsRtlDeleteTunnelCache**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md). In other words, a file system must ensure that it does not call **FsRtlFindInTunnelCache** and **FsRtlDeleteTunnelCache** at the same time from different threads.

## -see-also

[**FsRtlDeleteTunnelCache**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtldeletetunnelcache.md)

[**FsRtlInitializeTunnelCache**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlinitializetunnelcache.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)
