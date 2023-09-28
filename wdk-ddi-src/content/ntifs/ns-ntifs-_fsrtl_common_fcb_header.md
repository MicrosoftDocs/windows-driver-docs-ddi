---
UID: NS:ntifs._FSRTL_COMMON_FCB_HEADER
title: FSRTL_COMMON_FCB_HEADER (ntifs.h)
description: Learn more about the FSRTL_COMMON_FCB_HEADER structure.
tech.root: ifsk
ms.date: 09/27/2023
keywords: ["FSRTL_COMMON_FCB_HEADER structure"]
ms.keywords: "*PFSRTL_COMMON_FCB_HEADER, FSRTL_COMMON_FCB_HEADER, FSRTL_COMMON_FCB_HEADER structure [Installable File System Drivers], PFSRTL_COMMON_FCB_HEADER, PFSRTL_COMMON_FCB_HEADER structure pointer [Installable File System Drivers], _FSRTL_COMMON_FCB_HEADER, contextstructures_775f0b4a-8043-4125-85b4-530a79ed76ba.xml, ifsk.fsrtl_common_fcb_header, ntifs/FSRTL_COMMON_FCB_HEADER, ntifs/PFSRTL_COMMON_FCB_HEADER"
req.header: ntifs.h
req.include-header: Ntifs.h, Fltkernel.h
req.target-type: Windows
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
req.lib: 
req.dll: 
req.irql: 
targetos: Windows
req.typenames: FSRTL_COMMON_FCB_HEADER
f1_keywords:
 - _FSRTL_COMMON_FCB_HEADER
 - ntifs/_FSRTL_COMMON_FCB_HEADER
 - FSRTL_COMMON_FCB_HEADER
 - ntifs/FSRTL_COMMON_FCB_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FSRTL_COMMON_FCB_HEADER
 - FSRTL_COMMON_FCB_HEADER
---

# _FSRTL_COMMON_FCB_HEADER structure

## -description

Do not use the FSRTL_COMMON_FCB_HEADER structure outside of the [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure.  The FSRTL_COMMON_FCB_HEADER structure contains context information that a file system maintains about a file, directory, volume, or alternate data stream.

## -struct-fields

### -field NodeTypeCode

Reserved for system use.

### -field NodeByteSize

Reserved for system use.

### -field Flags

Bitmask of flags that indicate support for various features. This member must be a bitwise OR combination of one or more of the following values:

| Value | Meaning |
| ----- | ------- |
| FSRTL_FLAG_FILE_MODIFIED        | Reserved for system use. |
| FSRTL_FLAG_FILE_LENGTH_CHANGED  | Reserved for system use. |
| FSRTL_FLAG_LIMIT_MODIFIED_PAGES | Reserved for system use.  File system drivers (except for filter drivers) that must set or clear a limit of modified data for a file should call [**CcSetDirtyPageThreshold**](nf-ntifs-ccsetdirtypagethreshold.md).
| FSRTL_FLAG_ACQUIRE_MAIN_RSRC_EX | Reserved for system use. |
| FSRTL_FLAG_ACQUIRE_MAIN_RSRC_SH | Reserved for system use. |
| FSRTL_FLAG_USER_MAPPED_FILE     | The Cache Manager sets this flag to indicate that a view is mapped to a file. |
| FSRTL_FLAG_ADVANCED_HEADER      | This flag indicates that the file system is using [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) instead of FSRTL_COMMON_FCB_HEADER in its file control block (FCB) structures. This flag is required because use of the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure is deprecated. |
| FSRTL_FLAG_EOF_ADVANCE_ACTIVE | Reserved for system use. |

### -field IsFastIoPossible

This member must be one of the following values:

| Value | Meaning |
| ----- | ------- |
| **FastIoIsPossible**     | Fast I/O is possible. |
| **FastIoIsQuestionable** | An exclusive byte range lock exists for the file. The caller should call the file system's **FastIoCheckIfPossible** routine. |
| **FastIoIsNotPossible**  | The FCB for the file is bad, or an opportunistic lock (also called  "oplock") exists for the file. |

For more information about these values, see the reference entries for [**FsRtlAreThereCurrentFileLocks**](nf-ntifs-fsrtlaretherecurrentfilelocks.md), [**FsRtlCopyRead**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread.md), and [**FsRtlCopyWrite**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite.md).

### -field Flags2

Bitmask of flags that the file system sets to indicate support for various features. This member must be one or more of the following values:

| Value | Meaning |
| ----- | ------- |
| FSRTL_FLAG2_DO_MODIFIED_WRITE        | See details following this table. |
| FSRTL_FLAG2_PURGE_WHEN_MAPPED        | If this flag is set, the Cache Manager will flush and purge the cache map when a user first maps a file. |
| FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS | This flag indicates that the file system is using [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) instead of FSRTL_COMMON_FCB_HEADER in its FCB structures. This flag is required because use of the FSRTL_COMMON_FCB_HEADER structure outside of the **FSRTL_ADVANCED_FCB_HEADER** structure is deprecated. |
| FSRTL_FLAG2_IS_PAGING_FILE           | If set, this FCB header is associated with a page file. |

The FSRTL_FLAG2_DO_MODIFIED_WRITE flag is used together with the **FsContext2** member of the file object for the file stream as follows:

* If the **FsContext2** member of the file object is non-NULL, the file stream represents an open instance of a file or a directory, and the value of this flag is ignored by the operating system.

* If the **FsContext2** member of the file object is NULL, and this flag is not set, the file object is a stream file object, and the stream is a modified-no-write (MNW) stream.

* If the **FsContext2** member of the file object is NULL, and this flag is set, the file object is a stream file object, and the stream is writable.

### -field Reserved

Reserved for system use. Drivers must set this bit-field to zero.

### -field Version

Reserved for system use.  This bit-field is set by the [**FsRtlSetupAdvancedHeader**](/previous-versions/ff547257(v=vs.85)) or [**FsRtlSetupAdvancedHeaderEx**](nf-ntifs-fsrtlsetupadvancedheaderex.md) macro.  Starting with Windows Vista, the value of this bit-field is FSRTL_FCB_HEADER_V1 or greater; otherwise, the value is FSRTL_FCB_HEADER_V0.  See [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) for more information.

### -field Resource

Pointer to an initialized resource variable, for which the file system supplies the storage that will be used to synchronize I/O access to the FCB. The resource variable must be allocated from nonpaged pool.

Filter drivers should treat this member as opaque.

### -field PagingIoResource

Pointer to an additional resource variable, for which the file system supplies the storage that will be used to synchronize paging I/O access to the FCB. The resource variable must be allocated from nonpaged pool.

Filter drivers should treat this member as opaque.

### -field AllocationSize

Allocation size for the file stream.

For more information about the **AllocationSize**, **FileSize**, and **ValidDataLength** members, see [**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md).

### -field FileSize

File size of the file stream.

### -field ValidDataLength

Valid data length of the file stream.

## -remarks

File systems must set the **FsContext** member of every file object to point to an [**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md) structure. This structure can be embedded inside of a file-system-specific stream context object structure (the remainder of this structure is file-system-specific). Usually, the **FSRTL_ADVANCED_FCB_HEADER**  structure is a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, it is a stream control block (SCB).

To support filter manager and filter contexts, file systems must use the **FSRTL_ADVANCED_FCB_HEADER** structure in their stream context objects. All Microsoft file systems use this structure, and all third-party file system developers must do so as well. FCBs and SCBs for all classes of open requests, including volume open requests, must include this structure.

If the file is used as a paging file, the **FSRTL_ADVANCED_FCB_HEADER** structure must be allocated from nonpaged pool. Otherwise, it can be allocated from paged or nonpaged pool.

## -see-also

[**CcInitializeCacheMap**](nf-ntifs-ccinitializecachemap.md)

[**FSRTL_ADVANCED_FCB_HEADER**](ns-ntifs-_fsrtl_advanced_fcb_header.md)

[**FSRTL_PER_STREAM_CONTEXT**](/previous-versions/ff547357(v=vs.85))

[**FsRtlAreThereCurrentFileLocks**](nf-ntifs-fsrtlaretherecurrentfilelocks.md)

[**FsRtlCopyRead**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread.md)

[**FsRtlCopyWrite**](nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite.md)

[**FsRtlSetupAdvancedHeader**](/previous-versions/ff547257(v=vs.85))

[**FsRtlSetupAdvancedHeaderEx**](nf-ntifs-fsrtlsetupadvancedheaderex.md)
