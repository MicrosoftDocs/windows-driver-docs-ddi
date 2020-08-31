---
UID: NS:ntifs._FSRTL_COMMON_FCB_HEADER
title: _FSRTL_COMMON_FCB_HEADER (ntifs.h)
description: Do not use the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure.
old-location: ifsk\fsrtl_common_fcb_header.htm
tech.root: ifsk
ms.assetid: b0b199ea-d72f-4de3-a6b1-bd22140d13cb
ms.date: 04/16/2018
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
 - FSRTL_COMMON_FCB_HEADER
---

# _FSRTL_COMMON_FCB_HEADER structure


## -description

Do not use the FSRTL_COMMON_FCB_HEADER structure outside of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure.  The FSRTL_COMMON_FCB_HEADER structure contains context information that a file system maintains about a file, directory, volume, or alternate data stream.

## -struct-fields

### -field NodeTypeCode

Reserved for system use.

### -field NodeByteSize

Reserved for system use.

### -field Flags

Bitmask of flags that indicate support for various features. This member must be a bitwise OR combination of one or more of the following values:





#### FSRTL_FLAG_FILE_MODIFIED

Reserved for system use. 



#### FSRTL_FLAG_FILE_LENGTH_CHANGED

Reserved for system use. 



#### FSRTL_FLAG_LIMIT_MODIFIED_PAGES

Reserved for system use.  File system drivers (except for filter drivers) that must set or clear a limit of modified data for a file should call <a href="https://msdn.microsoft.com/library/windows/hardware/ff539209">CcSetDirtyPageThreshold</a>.



#### FSRTL_FLAG_ACQUIRE_MAIN_RSRC_EX

Reserved for system use. 



#### FSRTL_FLAG_ACQUIRE_MAIN_RSRC_SH

Reserved for system use. 



#### FSRTL_FLAG_USER_MAPPED_FILE

The Cache Manager sets this flag to indicate that a view is mapped to a file. 



#### FSRTL_FLAG_ADVANCED_HEADER

This flag indicates that the file system is using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> instead of FSRTL_COMMON_FCB_HEADER in its file control block (FCB) structures. This flag is required because use of the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure is deprecated.



#### FSRTL_FLAG_EOF_ADVANCE_ACTIVE

Reserved for system use.

### -field IsFastIoPossible

This member must be one of the following values: 

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
<b>FastIoIsPossible</b>

</td>
<td>
Fast I/O is possible. 

</td>
</tr>
<tr>
<td>
<b>FastIoIsQuestionable</b>

</td>
<td>
An exclusive byte range lock exists for the file. The caller should call the file system's <b>FastIoCheckIfPossible</b> routine. 

</td>
</tr>
<tr>
<td>
<b>FastIoIsNotPossible</b>

</td>
<td>
The FCB for the file is bad, or an opportunistic lock (also called  "oplock") exists for the file. 

</td>
</tr>
</table>
 

For more information about these values, see the reference entries for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlaretherecurrentfilelocks">FsRtlAreThereCurrentFileLocks</a>, <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>, and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite">FsRtlCopyWrite</a>.

### -field Flags2

Bitmask of flags that the file system sets to indicate support for various features. This member must be one or more of the following values: 





#### FSRTL_FLAG2_DO_MODIFIED_WRITE

This flag is used together with the <b>FsContext2</b> member of the file object for the file stream as follows: 

<ul>
<li>If the <b>FsContext2</b> member of the file object is non-<b>NULL</b>, the file stream represents an open instance of a file or a directory, and the value of this flag is ignored by the operating system.</li>
<li>If the <b>FsContext2</b> member of the file object is <b>NULL</b>, and this flag is not set, the file object is a stream file object, and the stream is a modified-no-write (MNW) stream.</li>
<li>If the <b>FsContext2</b> member of the file object is <b>NULL</b>, and this flag is set, the file object is a stream file object, and the stream is writable.</li>
</ul>


#### FSRTL_FLAG2_PURGE_WHEN_MAPPED

If this flag is set, the Cache Manager will flush and purge the cache map when a user first maps a file. 



#### FSRTL_FLAG2_SUPPORTS_FILTER_CONTEXTS

This flag indicates that the file system is using <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> instead of FSRTL_COMMON_FCB_HEADER in its FCB structures. This flag is required because use of the FSRTL_COMMON_FCB_HEADER structure outside of the FSRTL_ADVANCED_FCB_HEADER structure is deprecated.



#### FSRTL_FLAG2_IS_PAGING_FILE

If set, this FCB header is associated with a page file.

### -field Reserved

Reserved for system use. Drivers must set this bit-field to zero.

### -field Version

Reserved for system use.  This bit-field is set by the <a href="https://msdn.microsoft.com/library/windows/hardware/ff547257">FsRtlSetupAdvancedHeader</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlsetupadvancedheaderex">FsRtlSetupAdvancedHeaderEx</a> macro.  Starting with Windows Vista, the value of this bit-field is FSRTL_FCB_HEADER_V1 or greater; otherwise, the value is FSRTL_FCB_HEADER_V0.  See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> for more information.

### -field Resource

Pointer to an initialized resource variable, for which the file system supplies the storage that will be used to synchronize I/O access to the FCB. The resource variable must be allocated from nonpaged pool. 

Filter drivers should treat this member as opaque.

### -field PagingIoResource

Pointer to an additional resource variable, for which the file system supplies the storage that will be used to synchronize paging I/O access to the FCB. The resource variable must be allocated from nonpaged pool. 

Filter drivers should treat this member as opaque.

### -field AllocationSize

Allocation size for the file stream. 

For more information about the <b>AllocationSize</b>, <b>FileSize</b>, and <b>ValidDataLength</b> members, see <a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>.

### -field FileSize

File size of the file stream.

### -field ValidDataLength

Valid data length of the file stream.

## -remarks

File systems must set the <b>FsContext</b> member of every file object to point to an <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a> structure.  This structure can be embedded inside of a file-system-specific stream context object structure (the remainder of this structure is file-system-specific). Usually, the FSRTL_ADVANCED_FCB_HEADER  structure is a file control block (FCB). However, on some file systems that support multiple data streams, such as NTFS, it is a stream control block (SCB).

<div class="alert"><b>Note</b>   To support filter manager and filter contexts, file systems must use the FSRTL_ADVANCED_FCB_HEADER structure in their stream context objects. All Microsoft file systems use this structure, and all third-party file system developers must do so as well.  FCBs and SCBs for all classes of open requests, including volume open requests, must include this structure.</div>
<div> </div>
If the file is used as a paging file, the FSRTL_ADVANCED_FCB_HEADER structure must be allocated from nonpaged pool. Otherwise, it can be allocated from paged or nonpaged pool.

## -see-also

<a href="https://msdn.microsoft.com/library/windows/hardware/ff539135">CcInitializeCacheMap</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_fsrtl_advanced_fcb_header">FSRTL_ADVANCED_FCB_HEADER</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547357">FSRTL_PER_STREAM_CONTEXT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-fsrtlaretherecurrentfilelocks">FsRtlAreThereCurrentFileLocks</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopyread">FsRtlCopyRead</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-_fsrtl_advanced_fcb_header-fsrtlcopywrite">FsRtlCopyWrite</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff547257">FsRtlSetupAdvancedHeader</a>

