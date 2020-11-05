---
UID: NF:fltkernel.FltQueryDirectoryFile
title: FltQueryDirectoryFile function (fltkernel.h)
description: The FltQueryDirectoryFile routine returns various kinds of information about files in the directory specified by a given file object.
old-location: ifsk\fltquerydirectoryfile.htm
tech.root: ifsk
ms.assetid: d77dfcc7-a7a7-4027-9831-42b1b79738d0
ms.date: 04/16/2018
keywords: ["FltQueryDirectoryFile function"]
ms.keywords: FltQueryDirectoryFile, FltQueryDirectoryFile routine [Installable File System Drivers], fltkernel/FltQueryDirectoryFile, ifsk.fltquerydirectoryfile, FltQueryDirectoryFileEx
req.header: fltkernel.h
req.include-header: Fltkernel.h
req.target-type: Universal
req.target-min-winverclnt: This routine is available starting with Windows Vista.
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - FltQueryDirectoryFile
 - fltkernel/FltQueryDirectoryFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltQueryDirectoryFile
---

# FltQueryDirectoryFile function

## -description

The **FltQueryDirectoryFile** routine returns various kinds of information about files in the directory specified by a given file object. Use [FltQueryDirectoryFileEx](nf-fltkernel-fltquerydirectoryfileex.md) for greater query control.

## -parameters

### -param Instance

[in] Opaque pointer to the filter driver instance that initiates the I/O.

### -param FileObject

[in] Pointer to the file object that represents the directory to be scanned.

### -param FileInformation

[out] Pointer to a buffer that receives the desired information about the file. The structure of the information returned in the buffer is defined by the *FileInformationClass* parameter.

### -param Length

[in] Size, in bytes, of the buffer pointed to by *FileInformation*. The caller should set this parameter according to the given *FileInformationClass*.

### -param FileInformationClass

[in] Type of information to be returned about files in the directory. One of the values in the following table can be used.

| Value | Meaning |
| ----- | ------- |
| **FileBothDirectoryInformation** | Return a [**FILE_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_both_dir_information.md) structure for each file. |
| **FileDirectoryInformation** | Return a [**FILE_DIRECTORY_INFORMATION**](../ntifs/ns-ntifs-_file_directory_information.md) structure for each file. |
| **FileFullDirectoryInformation** | Return a [**FILE_FULL_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_full_dir_information.md) structure for each file. |
| **FileIdBothDirectoryInformation** | Return a [**FILE_ID_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_both_dir_information.md) structure for each file. |
| **FileIdExtdBothDirectoryInformation** | Return a [**FILE_ID_EXTD_BOTH_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_extd_both_dir_information.md) structure for each file. |
| **FileIdExtdDirectoryInformation** | Return a [**FILE_ID_EXTD_DIR_INFORMATION**](../ntifs/ns-ntifs-file_id_extd_dir_information.md) structure for each file. |
| **FileIdFullDirectoryInformation** | Return a [**FILE_ID_FULL_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_full_dir_information.md) structure for each file. |
| **FileIdGlobalTxDirectoryInformation** | Return a [**FILE_ID_GLOBAL_TX_DIR_INFORMATION**](../ntifs/ns-ntifs-_file_id_global_tx_dir_information.md) structure for each file. |
| **FileNamesInformation** | Return a [**FILE_NAMES_INFORMATION**](../ntifs/ns-ntifs-_file_names_information.md) structure for each file. |
| **FileObjectIdInformation** | Return a [**FILE_OBJECTID_INFORMATION**](../ntifs/ns-ntifs-_file_objectid_information.md) structure for each file that has an object ID on the volume. This information class is valid only for the special directory "\$Extend\$ObjId:$O:$INDEX_ALLOCATION" on NTFS volumes. |
| **FileQuotaInformation** | Return a single [**FILE_QUOTA_INFORMATION**](../ntifs/ns-ntifs-_file_quota_information.md) structure for each user on the volume that has quotas applied. This information class is valid only for the special directory "\$Extend\$Quota:$Q:$INDEX_ALLOCATION" on NTFS volumes. |
| **FileReparsePointInformation** | Return a single [**FILE_REPARSE_POINT_INFORMATION**](../ntifs/ns-ntifs-_file_reparse_point_information.md) structure for each file that has a reparse point on the volume. This information class is valid only for the special directory "\$Extend\$Reparse:$R:$INDEX_ALLOCATION" on NTFS and ReFS volumes. |

### -param ReturnSingleEntry

[in] Set to **TRUE** if only a single entry should be returned, **FALSE** otherwise. If this parameter is **TRUE**, **FltQueryDirectoryFile** returns only the first entry that is found.

### -param FileName

[in, optional] Pointer to a caller-allocated Unicode string that contains the name of a file (or multiple files, if wildcards are used) within the directory specified by *FileObject*. This parameter is optional and can be **NULL**.

If *FileName* is not **NULL**, only files whose names match the *FileName* string are included in the directory scan. If *FileName* is **NULL**, all files are included. If *RestartScan* is **FALSE**, the value of *FileName* is ignored.

### -param RestartScan

[in] Set to **TRUE** if the scan is to start at the first entry in the directory. Set to **FALSE** if resuming the scan from a previous call. The caller must set this parameter to **TRUE** when calling **FltQueryDirectoryFile** for the first time.

### -param LengthReturned

[out, optional] Receives the number of bytes actually written to the given *FileInformation* buffer.

## -returns

**FltQueryDirectoryFile** returns STATUS_SUCCESS or an appropriate error status. Note that the set of error status values that can be returned is file-system-specific.

## -remarks

**FltQueryDirectoryFile** returns information about files that are contained in the directory that is represented by *FileObject*.

The first call to **FltQueryDirectoryFile** determines the set of entries to be included in the directory scan for all subsequent calls, based on the values of *ReturnSingleEntry*, *FileName*, and *RestartScan*. If there is at least one matching entry, **FltQueryDirectoryFile** creates a FILE_*XXX*_INFORMATION structure (see the above table) for each entry in turn and stores the structure into the buffer.

Assuming that at least one matching directory entry is found, the number of entries for which information is returned is the smallest of the following:

* One entry, if *ReturnSingleEntry* is **TRUE** and *FileName* is **NULL**.  

* The number of entries that match the *FileName* string, if *FileName* is not **NULL**. (Note that if the string contains no wildcards, there can be at most one matching entry.)

* The number of entries whose information fits into the specified buffer.

* The number of entries contained in the directory.

On the first call to **FltQueryDirectoryFile**, if the structure created for the first entry found too large to fit into the output buffer, only the fixed portion of the structure is returned. The fixed portion consists of all fields of the structure except the final *FileName* string. On the first call, but not on subsequent ones, the I/O system ensures that the buffer is large enough to hold the fixed portion of the appropriate FILE_*XXX*_INFORMATION structure. When this happens, **FltQueryDirectoryFile** returns an appropriate status value such as STATUS_BUFFER_OVERFLOW.  Also on the first call to **FltQueryDirectoryFile**, if there is no file in the *FileObject* directory that matches the *FileName* parameter, **FltQueryDirectoryFile** returns an appropriate status value such as STATUS_NO_SUCH_FILE.

On each call, **FltQueryDirectoryFile** returns as many FILE_*XXX*_INFORMATION structures (one per directory entry) as can be contained entirely in the buffer pointed to by *FileInformation*. As long as the output buffer contains at least one complete structure, the status value returned is STATUS_SUCCESS. No information about any remaining entries is reported. Thus, except in the cases listed above where only one entry is returned, **FltQueryDirectoryFile** must be called at least twice to enumerate the contents of an entire directory (for example, when the *FileName* parameter contains one or more wildcard characters or is **NULL**).

The final call to **FltQueryDirectoryFile** returns an empty output buffer and reports an appropriate status value such as STATUS_NO_MORE_FILES.

> [!NOTE]
> When **FltQueryDirectoryFile** is called multiple times on the same directory, it is possible that the number of entries for which information is returned will be less than expected. This is because the set of entries to be included in the directory scan is fixed on the first call to **FltQueryDirectoryFile**. In subsequent calls, **FltQueryDirectoryFile** resumes the directory scan wherever it left off in this same enumeration. However, between calls to **FltQueryDirectoryFile**, the actual directory entries can change so that they are no longer in sync with the original enumeration.

**FltQueryDirectoryFile** returns zero in any member of a FILE_*XXX*_INFORMATION structure that is not supported by the file system.

For information about other file information query routines, see [File Objects](../index.yml).

Callers of **FltQueryDirectoryFile** must be running at IRQL = PASSIVE_LEVEL and with APCs enabled. For more information, see [Disabling APCs](/windows-hardware/drivers/kernel/disabling-apcs).

## -see-also

[FILE_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_both_dir_information.md)

[FILE_DIRECTORY_INFORMATION](../ntifs/ns-ntifs-_file_directory_information.md)

[FILE_FULL_DIR_INFORMATION](../ntifs/ns-ntifs-_file_full_dir_information.md)

[FILE_ID_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_both_dir_information.md)

[FILE_ID_EXTD_BOTH_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_extd_both_dir_information.md)

[FILE_ID_EXTD_DIR_INFORMATION](../ntifs/ns-ntifs-file_id_extd_dir_information.md)

[FILE_ID_FULL_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_full_dir_information.md)

[FILE_ID_GLOBAL_TX_DIR_INFORMATION](../ntifs/ns-ntifs-_file_id_global_tx_dir_information.md)

[FILE_NAMES_INFORMATION](../ntifs/ns-ntifs-_file_names_information.md)

[FILE_OBJECTID_INFORMATION](../ntifs/ns-ntifs-_file_objectid_information.md)

[FILE_QUOTA_INFORMATION](../ntifs/ns-ntifs-_file_quota_information.md)

[FILE_REPARSE_POINT_INFORMATION](../ntifs/ns-ntifs-_file_reparse_point_information.md)

[FltCreateFile](./nf-fltkernel-fltcreatefile.md)

[FltCreateFileEx](./nf-fltkernel-fltcreatefileex.md)

[FltCreateFileEx2](./nf-fltkernel-fltcreatefileex2.md)

[FltQueryDirectoryFileEx](nf-fltkernel-fltquerydirectoryfileex.md)

[IRP_MJ_DIRECTORY_CONTROL IRP](/windows-hardware/drivers/ifs/irp-mj-directory-control)

[UNICODE_STRING](/windows-hardware/drivers/ddi/wudfwdm/ns-wudfwdm-_unicode_string)

[ZwQueryDirectoryFile](https://msdn.microsoft.com/library/windows/hardware/ff567047")