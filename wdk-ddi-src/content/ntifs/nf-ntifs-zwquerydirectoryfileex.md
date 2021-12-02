---
UID: NF:ntifs.ZwQueryDirectoryFileEx
tech.root: kernel
title: ZwQueryDirectoryFileEx
ms.date: 11/03/2021
targetos: Windows
description: Learn more about the ZwQueryDirectoryFileEx function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.idl: 
req.include-header: 
req.irql: PASSIVE_LEVEL (see Remarks section)
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1709
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - DllExport
api_location:
 - ntifs.h
api_name:
 - ZwQueryDirectoryFileEx
f1_keywords:
 - ZwQueryDirectoryFileEx
 - ntifs/ZwQueryDirectoryFileEx
dev_langs:
 - c++
---

## -description

The **ZwQueryDirectoryFileEx** routine returns various information about files in the directory specified by a given file handle.

## -parameters

### -param FileHandle [in]

A handle returned by [**ZwCreateFile**](nf-ntifs-ntcreatefile.md) or [**ZwOpenFile**](nf-ntifs-ntopenfile.md) for the file object that represents the directory for which information is being requested. The file object must have been opened for asynchronous I/O if the caller specifies a non-NULL value for **Event** or **ApcRoutine**.

### -param Event [in, optional]

An optional handle for a caller-created event. If this parameter is supplied, the caller will be put into a wait state until the requested operation is completed and the given event is set to the Signaled state. This parameter is optional and can be NULL. It must be NULL if the caller will wait for the **FileHandle** to be set to the Signaled state.

### -param ApcRoutine [in, optional]

An address of an optional, caller-supplied APC routine to be called when the requested operation completes. This parameter is optional and can be NULL. If there is an I/O completion object associated with the file object, this parameter must be NULL.

### -param ApcContext [in, optional]

An optional pointer to a caller-determined context area if the caller supplies an APC or if an I/O completion object is associated with the file object. When the operation completes, this context is passed to the APC, if one was specified, or is included as part of the completion message that the I/O Manager posts to the associated I/O completion object.

This parameter is optional and can be NULL. It must be NULL if **ApcRoutine** is NULL and there is no I/O completion object associated with the file object.

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](../wdm/ns-wdm-_io_status_block.md) structure that receives the final completion status and information about the operation. For successful calls that return data, the number of bytes written to the **FileInformation** buffer is returned in the structure's **Information** member.

### -param FileInformation [out]

A pointer to an output buffer that receives the desired information about the file. The structure of the information returned in the buffer is defined by the **FileInformationClass** parameter.

### -param Length [in]

The size, in bytes, of the buffer pointed to by **FileInformation**. The caller should set this parameter according to the given **FileInformationClass**.

### -param FileInformationClass [in]

The type of information to be returned about files in the directory. See the **FileInformationClass** parameter of [**NtQueryDirectoryFileEx**](../ntifs/nf-ntifs-ntquerydirectoryfileex.md) for the list of possible values.

### -param QueryFlags [in]

One or more of the flags contained in SL_QUERY_DIRECTORY_MASK. See the **QueryFlags** parameter of [**NtQueryDirectoryFileEx**](../ntifs/nf-ntifs-ntquerydirectoryfileex.md) for the list of possible values.

### -param FileName [in, optional]

An optional pointer to a caller-allocated Unicode string containing the name of a file (or multiple files, if wildcards are used) within the directory specified by **FileHandle**. This parameter is optional:

* If **FileName** is not NULL, only files whose names match the **FileName** string are included in the directory scan.
* If **FileName** is NULL:
  * If SL_RETURN_SINGLE_ENTRY is not set in **QueryFlags**, all files are included.
  * If SL_RETURN_SINGLE_ENTRY is set, only one file is included.

The **FileName** is used as a search expression and is captured on the very first call to **ZwQueryDirectoryFileEx** for a given handle. Subsequent calls to **ZwQueryDirectoryFileEx** will use the search expression set in the first call. The **FileName** parameter passed to subsequent calls will be ignored.

## -returns

**ZwQueryDirectoryFileEx** returns STATUS_SUCCESS or an appropriate error status. The set of error status values that can be returned is file system-specific. **ZwQueryDirectoryFileEx** also returns the number of bytes actually written to the given **FileInformation** buffer in the **Information** member of **IoStatusBlock**. Some possible error codes and reasons might be the following:

| Return code | Meaning |
| ----------- | ------- |
| STATUS_BUFFER_OVERFLOW   | The output buffer isn't large enough to return the full filename. |
| STATUS_BUFFER_TOO_SMALL  | The output buffer isn't large enough for at least the base structure identified by **FileInformationClass**. |
| STATUS_INVALID_PARAMETER | One of the parameters is invalid for the file system. |
| STATUS_NOT_SUPPORTED     | For example, an unsupported ***FileInformationClass** was specified. |

## -remarks

**ZwQueryDirectoryFileEx** returns information about files that are contained in the directory represented by **FileHandle**.

If provided, **FileName** determines the entries that are included in the directory scan for all subsequent calls to **ZwQueryDirectoryFileEx** for a given **FileHandle**.

If there is at least one matching entry, **ZwQueryDirectoryFileEx** creates a **FILE_*XXX*_INFORMATION** structure for each entry and stores them in the buffer.

Assuming that at least one matching directory entry is found, the number of entries for which information is returned is the *smallest* of the following:

* One entry, if SL_RETURN_SINGLE_ENTRY is set in **QueryFlags** and **FileName** is NULL.
* The number of entries that match the **FileName** string, if **FileName** is not NULL. If the string contains no wildcards, there can be at most one matching entry.
* The number of entries whose information fits into the specified buffer.
* The number of entries contained in the directory.

On the first call to **ZwQueryDirectoryFileEx**, if the structure it creates for the first entry found is too large to fit into the output buffer, this routine does the following:

* Writes the fixed portion of the structure to **FileInformation**'s output buffer. The fixed portion consists of all fields except the final **FileName** string. On the first call, but not on subsequent calls, the I/O system ensures that the buffer is large enough to hold the fixed portion of the appropriate **FILE_*XXX*_INFORMATION** structure.
* Writes to the output buffer as much of the **FileName** string as will fit.
* Returns an appropriate status value such as STATUS_BUFFER_OVERFLOW.

On each call, **ZwQueryDirectoryFileEx** returns as many **FILE_*XXX*_INFORMATION** structures (one per directory entry) as can be contained entirely in the buffer pointed to by **FileInformation**:

* On the first call, **ZwQueryDirectoryFileEx** returns STATUS_SUCCESS only if the output buffer contains at least one complete structure.
* On subsequent calls, if the output buffer contains no structures, **ZwQueryDirectoryFileEx** returns STATUS_SUCCESS but sets **IoStatusBlock**->**Information** = 0 to notify the caller of this condition. In this case, the caller should allocate a larger buffer and call **ZwQueryDirectoryFileEx** again. No information about any remaining entries is reported. Thus, except in the cases listed above where only one entry is returned, **ZwQueryDirectoryFileEx** must be called at least twice to enumerate the contents of an entire directory.

When calling **ZwQueryDirectoryFileEx**, you might see changes made to the directory that occur in parallel with **ZwQueryDirectoryFileEx** calls.  This behavior is dependent on the implementation of the underlying file system.

The final call to **ZwQueryDirectoryFileEx** returns an empty output buffer and reports an appropriate status value such as STATUS_NO_MORE_FILES.

If **ZwQueryDirectoryFileEx** is called multiple times on the same directory and some other operation changes the contents of that directory, any changes might or might not be seen, depending on the timing of the operations.

**ZwQueryDirectoryFileEx** returns zero in any member of a **FILE_*XXX*_INFORMATION** structure that is not supported by the file system.

Callers of **ZwQueryDirectoryFileEx** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

For information about other file information query routines, see [File Objects](../_kernel/index.md#file-objects).

> [!NOTE]
> If the call to the **ZwQueryDirectoryFileEx** function occurs in user mode, you should use the name "**NtQueryDirectoryFileEx**" instead of "**ZwQueryDirectoryFileEx**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FILE_BOTH_DIR_INFORMATION**](ns-ntifs-_file_both_dir_information.md)

[**FILE_DIRECTORY_INFORMATION**](ns-ntifs-_file_directory_information.md)

[**FILE_FULL_DIR_INFORMATION**](ns-ntifs-_file_full_dir_information.md)

[**FILE_ID_BOTH_DIR_INFORMATION**](ns-ntifs-_file_id_both_dir_information.md)

[**FILE_ID_FULL_DIR_INFORMATION**](ns-ntifs-_file_id_full_dir_information.md)

[**FILE_NAMES_INFORMATION**](ns-ntifs-_file_names_information.md)

[**FILE_OBJECTID_INFORMATION**](ns-ntifs-_file_objectid_information.md)

[**FILE_REPARSE_POINT_INFORMATION**](ns-ntifs-_file_reparse_point_information.md)

[**UNICODE_STRING**](/windows/win32/api/ntdef/ns-ntdef-_unicode_string)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md)

[**ZwOpenFile**](../wdm/nf-wdm-zwopenfile.md)
