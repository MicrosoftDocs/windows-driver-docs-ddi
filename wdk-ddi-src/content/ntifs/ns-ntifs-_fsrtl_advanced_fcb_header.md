---
UID: NS:ntifs._FSRTL_ADVANCED_FCB_HEADER
title: FSRTL_ADVANCED_FCB_HEADER (ntifs.h)
description: The FSRTL_ADVANCED_FCB_HEADER structure contains context information that a file system maintains about a file.
old-location: ifsk\fsrtl_advanced_fcb_header.htm
tech.root: ifsk
ms.date: 09/28/2021
keywords: ["FSRTL_ADVANCED_FCB_HEADER structure"]
ms.keywords: "*PFSRTL_ADVANCED_FCB_HEADER, *PFSRTL_UNC_PROVIDER_REGISTRATION, FSRTL_ADVANCED_FCB_HEADER, FSRTL_ADVANCED_FCB_HEADER structure [Installable File System Drivers], FSRTL_UNC_PROVIDER_REGISTRATION, PFSRTL_ADVANCED_FCB_HEADER, PFSRTL_ADVANCED_FCB_HEADER structure pointer [Installable File System Drivers], _FSRTL_ADVANCED_FCB_HEADER, contextstructures_cede2315-2c72-496f-a192-3ef25a8b0516.xml, ifsk.fsrtl_advanced_fcb_header, ntifs/FSRTL_ADVANCED_FCB_HEADER, ntifs/PFSRTL_ADVANCED_FCB_HEADER"
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
req.typenames: FSRTL_ADVANCED_FCB_HEADER, FSRTL_UNC_PROVIDER_REGISTRATION, *PFSRTL_UNC_PROVIDER_REGISTRATION
f1_keywords:
 - _FSRTL_ADVANCED_FCB_HEADER
 - ntifs/_FSRTL_ADVANCED_FCB_HEADER
 - FSRTL_ADVANCED_FCB_HEADER
 - ntifs/FSRTL_ADVANCED_FCB_HEADER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _FSRTL_ADVANCED_FCB_HEADER
 - FSRTL_ADVANCED_FCB_HEADER
---

# FSRTL_ADVANCED_FCB_HEADER structure

## -description

The **FSRTL_ADVANCED_FCB_HEADER** structure contains context information that a file system maintains about a file.

## -struct-fields

### -field DUMMYUNIONNAME.DUMMYSTRUCTNAME

An unnamed member that contains a structure of type [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md).

### -field FastMutex

A pointer to an initialized fast mutex that is used to synchronize access to the following members of **DUMMYSTRUCTNAME**:

* **AllocationSize**
* **FileSize**
* **ValidDataLength**

If present, the **PushLock** member is used to synchronize access to the **FilterContexts** member; otherwise, **FastMutex** is used.

### -field FileContextSupportPointer

A pointer to a pointer field used by the file system runtime library (FSRTL) to track file contexts. If not **NULL**, this member must be a pointer to a PVOID variable inside a per-file structure for the file system that created the structure.  If **NULL**, file contexts are not supported.  This member is only available starting with Windows Vista (that is, if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V1**).

### -field FilterContexts

A pointer to the head of a list of all context structures that are associated with the file. Filter drivers can search this list by calling [**FsRtlLookupPerStreamContext**](nf-ntifs-fsrtllookupperstreamcontext.md) and modify it by calling [**FsRtlInsertPerStreamContext**](nf-ntifs-fsrtlinsertperstreamcontext.md) and [**FsRtlRemovePerStreamContext**](nf-ntifs-fsrtlremoveperstreamcontext.md).

### -field Oplock

The oplock for the file or directory. This field is only available starting with Windows 8 (that is, if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V2**).

### -field PushLock

A push lock used to synchronize access to the **FilterContexts** list. This field is only available starting with Windows Vista (that is, if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V1**).

### -field ReservedForRemote

If the file system is remote, this field is reserved. It is only available starting with Windows 8 (that is, if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V2**).

### -field AePushLock

An auto-expand push lock that is used instead of **PushLock** to synchronize access to the list of stream contexts. See **Remarks** for details.

**AePushlock** is available starting with Windows 10, version 20H2 (that is, if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V3**), and must be initialized by calling [**FsRtlSetupAdvancedHeaderEx2**](nf-ntifs-fsrtlsetupadvancedheaderex2.md).

### -field ReservedContext

This field is reserved for system use. It is only used in Windows 8.1 through Windows 10, version 1803 (if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V3**).

### -field BypassIoOpenCount

Tracks how many handles are currently open with [BypassIO](/windows-hardware/drivers/ifs/bypassio) enabled on this stream.

This field is available starting in Windows 11 (that is, if the **Version** bit-field of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure is greater than or equal to **FSRTL_FCB_HEADER_V4**).

## -remarks

The **FSRTL_ADVANCED_FCB_HEADER** structure is a superset of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure. File systems (including legacy filter and minifilter drivers, when applicable) must use the **FSRTL_ADVANCED_FCB_HEADER** structure.

File systems must use one of the following macros to initialize the **FSRTL_ADVANCED_FCB_HEADER** structure:

* [**FsRtlSetupAdvancedHeader**](/previous-versions/ff547257(v=vs.85))
* [**FsRtlSetupAdvancedHeaderEx**](nf-ntifs-fsrtlsetupadvancedheaderex.md)
* [**FsRtlSetupAdvancedHeaderEx2**](nf-ntifs-fsrtlsetupadvancedheaderex2.md), available starting in Windows 10, version 20H2.

The following flags are set by these macros.

| Flag | Meaning |
| ---- | ------- |
| FSRTL_FLAG_ADVANCED_HEADER | Set in the **Flags** member of the [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) structure, this flag indicates file system driver support for **FSRTL_ADVANCED_FCB_HEADER** structures.  This flag should not be modified. |
| FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS | Set in the **Flags2** member of [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md), this flag indicates support for filter driver contexts.  This flag can only be cleared for paging files (see information after the table). |

File systems must set the **FsContext** member of every file object to point to an **FSRTL_ADVANCED_FCB_HEADER** structure. This structure can be embedded inside of a context object structure that is specific to a file-system stream  (the remainder of the structure is file-system–specific). Usually, this structure is a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, it is a stream control block (SCB).  Note that FCBs and SCBs for all classes of open requests, including volume open requests, must include this structure.

If the file is a paging file, the **FSRTL_ADVANCED_FCB_HEADER** structure must be allocated from a nonpaged pool. Otherwise, it can be allocated from a paged or nonpaged pool.

All Microsoft file systems disable stream context support for paging files by clearing the **FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS** flag in the **Flags2** member of [**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md) after they call [**FsRtlSetupAdvancedHeader**](/previous-versions/ff547257(v=vs.85)). (See the **FatCreateFcb** function in *Strucsup.c* for the FASTFAT WDK sample.) You are strongly encouraged to do the same in your file system or systems so that the operating system will behave in a consistent manner across all file systems.

### Auto-expand push locks

Auto-expand push locks were introduced in Windows 10, version 20H2. When Filter Manager’s locks were originally designed, large multi-processor systems were very uncommon and RAM was precious. With such systems now common and RAM not as limited, auto-expand push locks provide a beneficial trade-off between memory consumption and speed.

An auto-expand push lock can automatically change from a regular non-cache-aware push lock into a cache-aware push lock when it detects that it is subject to high cache contention due to a large number of concurrent shared acquirers. The auto-expand push lock is larger than a normal push lock when not expanded, but not nearly as large as a cache-aware push lock. This push lock type is more performant on multiprocessor systems.

## -see-also

[**FSRTL_COMMON_FCB_HEADER**](ns-ntifs-_fsrtl_common_fcb_header.md)

[**FSRTL_PER_STREAM_CONTEXT**](/previous-versions/ff547357(v=vs.85))

[**FsRtlInsertPerStreamContext**](nf-ntifs-fsrtlinsertperstreamcontext.md)

[**FsRtlLookupPerStreamContext**](nf-ntifs-fsrtllookupperstreamcontext.md)

[**FsRtlRemovePerStreamContext**](nf-ntifs-fsrtlremoveperstreamcontext.md)

[**FsRtlSetupAdvancedHeader**](/previous-versions/ff547257(v=vs.85))

[**FsRtlSetupAdvancedHeaderEx**](nf-ntifs-fsrtlsetupadvancedheaderex.md)

[**FsRtlSetupAdvancedHeaderEx2**](nf-ntifs-fsrtlsetupadvancedheaderex2.md)

[**FsRtlTeardownPerStreamContexts**](nf-ntifs-fsrtlteardownperstreamcontexts.md)
