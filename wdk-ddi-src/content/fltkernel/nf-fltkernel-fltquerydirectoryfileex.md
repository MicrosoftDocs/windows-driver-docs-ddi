---
UID: NF:fltkernel.FltQueryDirectoryFileEx
title: FltQueryDirectoryFileEx function
description: FltQueryDirectoryFileEx returns various kinds of information about files in the directory specified by a given file object.
tech.root: ifsk
ms.date: 03/08/2019
keywords: ["FltQueryDirectoryFileEx function"]
ms.keywords: FltQueryDirectoryFileEx, FltQueryDirectoryFile
req.header: fltkernel.h
req.include-header: 
req.target-type: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.lib: 
req.dll: 
req.irql: 
req.ddi-compliance: 
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
targetos: Windows
f1_keywords:
 - FltQueryDirectoryFileEx
 - fltkernel/FltQueryDirectoryFileEx
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltQueryDirectoryFileEx
product:
 - Windows
---

# FltQueryDirectoryFileEx function


## -description

**FltQueryDirectoryFileEx** returns various kinds of information about files in the directory specified by a given file object.

## -parameters

### -param Instance

Opaque pointer to the minifilter driver instance that is initiating this I/O.

### -param FileObject

Pointer to the file object that represents the directory being queried.

### -param FileInformation

Pointer to a buffer that receives the desired information about the file. The structure of the information returned in the buffer is defined by the *FileInformationClass* parameter.

### -param Length

Size, in bytes, of the buffer pointed to by *FileInformation*. The caller should set this parameter according to the given *FileInformationClass*.

### -param FileInformationClass

Type of information to be returned about files in the directory. One of the values in the following table can be specified.

| Value | Meaning |
| ----- | ------- |
| **FileBothDirectoryInformation** | Return a [FILE_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_both_dir_information.md#requirements) structure for each file. |
| **FileDirectoryInformation** | Return a [FILE_DIRECTORY_INFORMATION](../ntifs/ns-ntifs-_file_directory_information.md#requirements) structure for each file. |
| **FileFullDirectoryInformation** | Return a [FILE_FULL_DIR_INFORMATION](../ntifs/ns-ntifs-_file_full_dir_information.md#requirements) structure for each file. |
| **FileIdBothDirectoryInformation** | Return a [FILE_ID_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_both_dir_information.md#requirements) structure for each file. |
| **FileIdExtdBothDirectoryInformation** | Return a [FILE_ID_EXTD_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_extd_both_dir_information.md#requirements) structure for each file. |
| **FileIdExtdDirectoryInformation** | Return a [FILE_ID_EXTD_DIR_INFO](/windows/win32/api/winbase/ns-winbase-file_id_extd_dir_info) structure for each file. |
| **FileIdFullDirectoryInformation** | Return a [FILE_ID_FULL_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_full_dir_information.md#requirements) structure for each file. |
| **FileIdGlobalTxDirectoryInformation** | Return a [FILE_ID_GLOBAL_TX_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_global_tx_dir_information.md#requirements) structure for each file. |
| **FileNamesInformation** | Return a [FILE_NAMES_INFORMATION](../ntifs/ns-ntifs-_file_names_information.md#requirements) structure for each file. |
| **FileObjectIdInformation** | Return a [FILE_OBJECTID_INFORMATION](../ntifs/ns-ntifs-_file_objectid_information.md#requirements) structure for each file that has an object ID on the volume. This information class is valid only for the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION" on NTFS volumes. |
| **FileQuotaInformation** | Return a single [FILE_QUOTA_INFORMATION](../ntifs/ns-ntifs-_file_quota_information.md#requirements) structure for each user on the volume that has quotas applied. This information class is valid only for the special directory "\$Extend\$Quota:$Q:$INDEX_ALLOCATION" on NTFS volumes. |
| **FileReparsePointInformation** | Return a single [FILE_REPARSE_POINT_INFORMATION](../ntifs/ns-ntifs-_file_reparse_point_information.md#requirements) structure for each file that has a reparse point on the volume. This information class is valid only for the special directory "\$Extend\$Reparse:$R:$INDEX_ALLOCATION" on NTFS and ReFS volumes. |

### -param QueryFlags

One or more of the flags contained in SL_QUERY_DIRECTORY_MASK. Possible values are specified in the following table.

| Value | Meaning |
| ----- | ------- |
| **SL_RESTART_SCAN** (0x00000001) | If this flag is set, the scan will start at the first entry in the directory. If this flag is not set, the scan will resume from where the last query ended. |
| **SL_RETURN_SINGLE_ENTRY** (0x00000002) | Normally the return buffer is packed with as many matching directory entries that fit. If this flag is set, the file system will return only one directory entry at a time. This does make the operation less efficient. |
| **SL_INDEX_SPECIFIED** (0x00000004) | If this flag is set, the scan should start at a specified indexed position in the directory. This flag can only be set if you generate your own [IRP_MJ_DIRECTORY_CONTROL IRP](/windows-hardware/drivers/ifs/irp-mj-directory-control); the index is specified in the IRP. How the position is specified varies from file system to file system. |
| **SL_RETURN_ON_DISK_ENTRIES_ONLY** (0x00000008) | If this flag is set, any file system filters that perform directory virtualization or just-in-time expansion should simply pass the request through to the file system and return entries that are currently on disk. Not all file systems support this flag. |
| **SL_NO_CURSOR_UPDATE_QUERY** (0x00000010) | File systems maintain per-*FileObject* directory cursor information. When multiple threads do queries using the same *FileObject*, access to the per-*FileObject* structure is single threaded to prevent corruption of the cursor state. This flag tells the file system to not update per-*FileObject* cursor state information thus allowing multiple threads to query in parallel using the same handle. It behaves as if SL_RESTART_SCAN is specified on each call. If a wild card pattern is given on the next call, the operation will not pick up where the last query ended. This allows for true asynchronous directory query support. If this flag is used inside a TxF transaction the operation will be failed. Not all file systems support this flag. |

### -param FileName

Pointer to a caller-allocated [UNICODE_STRING](/windows/win32/api/ntdef/ns-ntdef-_unicode_string) structure with the Unicode string that contains the name of a file (or multiple files, if wildcards are used) within the directory specified by *FileObject*. This parameter is optional and can be **NULL**. If *fileName* is **NULL**, all files are included.

If *FileName* is not **NULL**, only files whose names match the *FileName* string are included in the directory scan. If the *QueryFlags* **ResetScan** flag is set, the value of *FileName* is ignored.

### -param LengthReturned

Receives the number of bytes actually written to the given *FileInformation* buffer.

## -returns

**FltQueryDirectoryFileEx** returns STATUS_SUCCESS or an appropriate error code. The set of error status values that can be returned is file system-specific.

## -remarks

**FltQueryDirectoryFileEx** returns information about files that are contained in the directory represented by *FileObject*.

The first call to **FltQueryDirectoryFileEx** determines the set of entries to be included in the directory scan for all subsequent calls, based on the values of *QueryFlags* and *FileName*. If there is at least one matching entry, **FltQueryDirectoryFileEx** creates a FILE_*XXX*_INFORMATION structure (see the above table) for each entry in turn and stores the structure in the buffer.

Assuming that at least one matching directory entry is found, the number of entries for which information is returned is the smallest of the following:

* One entry, if the SL_RETURN_SINGLE_ENTRY flag is set in *QueryFlags* and *FileName* is **NULL**.  

* The number of entries that match the *FileName* string, if *FileName* is not **NULL**. (Note that if the string contains no wildcards, there can be at most one matching entry.)

* The number of entries whose information fits in the buffer pointed to by *FileInformation*.

* The number of entries contained in the directory.

On the first call to **FltQueryDirectoryFileEx**, if the structure created for the first found entry is too large to fit into the output buffer, only the fixed portion of the structure is returned. The fixed portion consists of all fields of the structure except the final *FileName* string. The I/O subsystem ensures that the buffer is large enough to hold the fixed portion of the appropriate FILE_*XXX*_INFORMATION structure (only on the first call and not on subsequent calls). When this happens, **FltQueryDirectoryFileEx** returns a status value of STATUS_BUFFER_OVERFLOW.  Also on the first call to **FltQueryDirectoryFileEx**, if there is no file in the *FileObject* directory that matches the *FileName* parameter, **FltQueryDirectoryFileEx** returns STATUS_NO_SUCH_FILE.

On each call, **FltQueryDirectoryFileEx** returns as many FILE_*XXX*_INFORMATION structures (one per directory entry) as can be contained entirely in the buffer pointed to by *FileInformation*. As long as the output buffer contains at least one complete structure, the status value returned is STATUS_SUCCESS. No information about any remaining entries is reported. Thus, except in the cases listed above where only one entry is returned, **FltQueryDirectoryFileEx** must be called at least twice to enumerate the contents of an entire directory (for example, when the *FileName* parameter contains one or more wildcard characters or is **NULL**).

The final call to **FltQueryDirectoryFileEx** returns an empty output buffer and reports a non-error status value of STATUS_NO_MORE_FILES.

**Note:** When **FltQueryDirectoryFileEx** is called multiple times on the same directory, it is possible that the number of entries for which information is returned will be less than expected. This is because the set of entries to be included in the directory scan is fixed on the first call to **FltQueryDirectoryFileEx**. In subsequent calls, **FltQueryDirectoryFileEx** resumes the directory scan wherever it left off in this same enumeration. However, between calls to **FltQueryDirectoryFileEx**, the actual directory entries can change so that they are no longer in sync with the original enumeration.

**FltQueryDirectoryFileEx** returns zero in any member of a FILE_*XXX*_INFORMATION structure that is not supported by the file system.

Callers of **FltQueryDirectoryFileEx** must be running at IRQL = PASSIVE_LEVEL and with APCs enabled. For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[FILE_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_both_dir_information.md)

[FILE_DIRECTORY_INFORMATION](../ntifs/ns-ntifs-_file_directory_information.md)

[FILE_FULL_DIR_INFORMATION](../ntifs/ns-ntifs-_file_full_dir_information.md)

[FILE_ID_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_both_dir_information.md)

[FILE_ID_EXTD_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_extd_both_dir_information.md)

[FILE_ID_EXTD_DIR_INFO](/windows/win32/api/winbase/ns-winbase-file_id_extd_dir_info)

[FILE_ID_FULL_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_full_dir_information.md)

[FILE_ID_GLOBAL_TX_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_global_tx_dir_information.md)

[FILE_NAMES_INFORMATION](../ntifs/ns-ntifs-_file_names_information.md)

[FILE_OBJECTID_INFORMATION](../ntifs/ns-ntifs-_file_objectid_information.md)

[FILE_QUOTA_INFORMATION](../ntifs/ns-ntifs-_file_quota_information.md)

[FILE_REPARSE_POINT_INFORMATION](../ntifs/ns-ntifs-_file_reparse_point_information.md)

[FltCreateFile](./nf-fltkernel-fltcreatefile.md)

[FltCreateFileEx](./nf-fltkernel-fltcreatefileex.md)

[FltCreateFileEx2](./nf-fltkernel-fltcreatefileex2.md)

[FltQueryDirectoryFile](./nf-fltkernel-fltquerydirectoryfile.md)

[IRP_MJ_DIRECTORY_CONTROL IRP](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[UNICODE_STRING](/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_unicode_string)

[ZwQueryDirectoryFile](https://msdn.microsoft.com/library/windows/hardware/ff567047")
