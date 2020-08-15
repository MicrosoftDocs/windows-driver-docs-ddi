---
UID: NF:fltkernel.FltGetFileNameInformation
title: FltGetFileNameInformation function (fltkernel.h)
description: The FltGetFileNameInformation routine returns name information for a file or directory.
old-location: ifsk\fltgetfilenameinformation.htm
tech.root: ifsk
ms.assetid: 707e7e83-31d8-46cf-a2ef-e53a20edaeff
ms.date: 07/27/2020
keywords: ["FltGetFileNameInformation function"]
ms.keywords: FltApiRef_e_to_o_1ce08fd0-5e23-43de-b012-dd71086282ea.xml, FltGetFileNameInformation, FltGetFileNameInformation routine [Installable File System Drivers], fltkernel/FltGetFileNameInformation, ifsk.fltgetfilenameinformation
f1_keywords:
 - "fltkernel/FltGetFileNameInformation"
 - "FltGetFileNameInformation"
req.header: fltkernel.h
req.include-header: Fltkernel.h
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
req.lib: FltMgr.lib
req.dll: Fltmgr.sys
req.irql: <= APC_LEVEL (See Return Value)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetFileNameInformation
targetos: Windows
req.typenames: 
---

# FltGetFileNameInformation function

## -description

The **FltGetFileNameInformation** routine returns name information for a file or directory.

## -parameters

### -param CallbackData 
[in]
Pointer to a [FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md) structure, which is the callback data structure for the I/O operation. This parameter is required and cannot be **NULL**.

### -param NameOptions 
[in]
A [**FLT_FILE_NAME_OPTIONS**](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options) value containing flags that specify the format of the name information to be returned, as well as the query method that the Filter Manager is to use. (Additional flags can be used by name provider minifilter drivers to specify name query options.) This parameter is required and cannot be **NULL**.

The following are the file name format flag values. Only one of the following flags can be specified. For an explanation of these formats, see [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md).

| Name Format Flag Value | Meaning |
| ----- | ------- |
| FLT_FILE_NAME_NORMALIZED | The *FileNameInformation* parameter receives the address of a structure containing the normalized name for the file. |
| FLT_FILE_NAME_OPENED | The *FileNameInformation* parameter receives the address of a structure containing the name that was used when the file was opened. |
| FLT_FILE_NAME_SHORT | The *FileNameInformation* parameter receives the address of a structure containing the short (8.3) name for the file. The short name consists of up to 8 characters, followed immediately by a period and up to 3 more characters. The short name for a file does not include the volume name, directory path, or stream name. Not valid in the pre-create path. |

Following are the file name query method flag values. Only one of the following flags can be specified.

| Query Method Flag Value | Meaning |
| ----- | ------- |
| FLT_FILE_NAME_QUERY_DEFAULT | If it is not currently safe to query the file system for the file name, **FltGetFileNameInformation** does nothing. Otherwise, **FltGetFileNameInformation** queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, **FltGetFileNameInformation** queries the file system and caches the result. |
| FLT_FILE_NAME_QUERY_CACHE_ONLY | **FltGetFileNameInformation** queries the Filter Manager's name cache for the file name information. **FltGetFileNameInformation** does not query the file system. |
| FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY | **FltGetFileNameInformation** queries the file system for the file name information. **FltGetFileNameInformation** does not query the Filter Manager's name cache, and does not cache the result of the file system query. |
| FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP | **FltGetFileNameInformation** queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, and it is currently safe to do so, **FltGetFileNameInformation** queries the file system for the file name information and caches the result. |

Name provider minifilters use the following flags to specify the properties of file name operations.

| Name Provider Flag Value | Meaning |
| ----- | ------- |
| FLT_FILE_NAME_REQUEST_FROM_CURRENT_PROVIDER | A name provider minifilter can use this flag to specify that a name query request should be redirected to itself (the name provider minifilter) rather than being satisfied by the name providers lower in the stack. |
| FLT_FILE_NAME_DO_NOT_CACHE | This flag denotes that the name retrieved from this query should not be cached. Name provider minifilters use this flag as they perform intermediate queries to generate a name. |
| FLT_FILE_NAME_ALLOW_QUERY_ON_REPARSE | A name provider minifilter can use this flag to specify that it is safe to query the name in the post-create path even if STATUS_REPARSE was returned. It is the caller's responsibility to ensure that the **FileObject->FileName** field was not changed. Do not use this flag with mount points or symbolic link reparse points. |

### -param FileNameInformation 
[out]
Pointer to a caller-allocated variable that receives the address of a system-allocated [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md) structure containing the file name information. **FltGetFileNameInformation** allocates this structure from paged pool. This parameter is required and cannot be **NULL**.

## -returns

If the name information is successfully returned, **FltGetFileNameInformation** returns STATUS_SUCCESS. Otherwise, it returns an appropriate NTSTATUS value such as one of the following:

<table>
<tr>
<th>Return code</th>
<th>Description</th>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_INVALID_NAME_REQUEST</b></dt>
</dl>
</td>
<td width="60%">

<b>FltGetFileNameInformation</b> cannot get file name information in any of the following circumstances if the query cannot be satisfied from Filter Manager’s name cache:
<ul>
<li>
In the paging I/O path.
</li>

<li>
When the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information about this issue, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp">IoGetTopLevelIrp</a>.)
</li>

<li>
After an <a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup">IRP_MJ_CLEANUP</a> operation is completed; that is, in the post-clean up, pre-close, or post-close path (the target file object has the FO_CLEANUP_COMPLETE flag set).
</li>

<li>
In a preoperation (PFLT_PRE_OPERATION_CALLBACK) or postoperation (PFLT_POST_OPERATION_CALLBACK) callback routine for any of the following operations:
<ul>
<li>IRP_MJ_ACQUIRE_FOR_CC_FLUSH</li>
<li>IRP_MJ_ACQUIRE_FOR_MOD_WRITE
<li>IRP_MJ_RELEASE_FOR_CC_FLUSH</li>
<li>IRP_MJ_RELEASE_FOR_MOD_WRITE</li>
<li>IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION</li>
</ul>
</li>

<li>
In a postoperation callback routine for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION.
</li>

<li>
When all APCs are disabled; that is, when <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keareallapcsdisabled">KeAreAllApcsDisabled</a> returns TRUE.
</li>

</ul>

<b>FltGetFileNameInformation</b> cannot get the short name of a file in the pre-create path.

STATUS_FLT_INVALID_NAME_REQUEST is an error code.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltGetFileNameInformation</b> encountered a pool allocation failure. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
Returned when an invalid parameter is passed, such as one of the following:

<ul>
<li>
The <b>FileNameInformation</b> parameter cannot be <b>NULL</b>.

</li>
<li>
The <i>CallbackData</i> parameter cannot be <b>NULL</b>.

</li>
</ul>
STATUS_INVALID_PARAMETER is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_FLT_NAME_CACHE_MISS</b></dt>
</dl>
</td>
<td width="60%">
The file name information is not found in the name cache and <i>NameOptions</i> includes FLT_FILE_NAME_QUERY_CACHE_ONLY.

-or-

The file name information is not found in the name cache when <i>NameOptions</i> includes FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP and the file name information cannot be queried from the file system.

An additional call to <b>FltGetFileNameInformation</b>  with FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY set in <i>NameOptions</i> may return the file name information.

</td>
</tr>

<tr>
<td>
<dl>
<dt><b>STATUS_NOT_SAME_DEVICE</b></dt>
</dl>
</td>
<td>The file being queried during pre-create is on a different volume than its parent directory. This error is returned for normalized name queries, where the file was a junction or symlink that resolved to a different volume.
</td>
</tr>

<tr>
<td width="40%">
<dl>
<dt><b>STATUS_ACCESS_DENIED</b></dt>
</dl>
</td>
<td width="60%">
If the user opened the file by file ID but does not have traverse privileges for the entire path, <b>FltGetFileNameInformation</b> fails with this return value.

STATUS_ACCESS_DENIED is an error code.

-or-

The file is a system file with all access denied.

</td>
</tr>
</table>

## -remarks

**FltGetFileNameInformation** returns the requested name information for the file or directory that is the target of the operation described by *CallbackData*, in the specified format. The file or directory does not need to be opened yet by the file system.

For a pre-create operation, if the **CallbackData->Iopb->OperationFlags** member contains the SL_OPEN_TARGET_DIRECTORY bitwise flag, **FltGetFileNameInformation** returns the name of the containing (parent) directory for the given file. This name is the actual path that the create operation opens.

To parse the contents of the FLT_FILE_NAME_INFORMATION structure returned by **FltGetFileNameInformation**, call [FltParseFileNameInformation](nf-fltkernel-fltparsefilenameinformation.md). (For more information about file name formats, see [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md).)

After a successful call to **FltGetFileNameInformation**, the caller is responsible for releasing the pointer returned in the *FileNameInformation* parameter when the pointer is no longer needed. The caller does this by calling [FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md).

The caller must not modify the contents of the structure returned in the *FileNameInformation* parameter because this structure is cached by the Filter Manager so that all minifilter drivers can use it.

If **FltGetFileNameInformation** is called in the preoperation callback routine for a create operation to retrieve the opened name, **FltGetFileNameInformation** succeeds even if the path to the file being opened does not exist on the volume.

If **FltGetFileNameInformation** is called in the preoperation callback routine for a create operation to retrieve the normalized name, **FltGetFileNameInformation** succeeds even if the final component of the path to the file being opened does not exist on the volume.

> [!NOTE]
>
> Starting in Windows 10, you cannot query normalized file names on a remote volume because the Server Message Block (SMB) Protocol does not support queries for normalized paths.

In create, hard-link, and rename operations, file name tunneling can cause the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine to be invalidated. If a minifilter driver retrieves normalized file name information in a preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)) routine by calling a routine such as **FltGetFileNameInformation**, it must call [FltGetTunneledName](nf-fltkernel-fltgettunneledname.md) from its postoperation callback ([PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)) routine to retrieve the correct file name information for the file.

For Windows 8.1 and earlier, **FltGetFileNameInformation** can include a [stream type](https://docs.microsoft.com/windows/desktop/FileIO/file-streams) *only* when called from a filter’s pre-create callback. To distinguish between a file’s default stream and metadata streams, this call should be made in the pre-create operation. The resulting stream type will remain valid across the lifetime of the file.

 Prior to Windows 8, Filter Manager obtained the normalized name for a file or directory by collecting the name information for each component of  the file path. This required multiple queries to the file system to compile the complete path. Starting with Windows 8, local file systems support the  **FileNormalizedNameInformation** file information class and only a single query is necessary to obtain the normalized name. Remote file systems may not support the **FileNormalizedNameInformation** file information class. When this is the case, a query for each component of the file path is still required to assemble the normalized name. Under certain network conditions, a full name query can require a significant amount of time to complete.

For more information about normalized file name information, see [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md).

> [!NOTE]
>
> File name tunneling affects only create, hard-link, and rename operations in this way. It does not affect other I/O operations, such as read and write.

The following paired operations can cause the file name *name* to be tunneled:

* delete (*name*)/create(*name*)
* delete (*name*)/rename(*source, name*)
* rename (*name, newname*)/create(*name*)
* rename (*name, newname*)/rename(*source,name*)

## -see-also

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md)

[FLT_FILE_NAME_OPTIONS](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options)

[FltGetDestinationFileNameInformation](nf-fltkernel-fltgetdestinationfilenameinformation.md)

[FltGetFileNameInformationUnsafe](nf-fltkernel-fltgetfilenameinformationunsafe.md)

[FltGetTunneledName](nf-fltkernel-fltgettunneledname.md)

[FltParseFileNameInformation](nf-fltkernel-fltparsefilenameinformation.md)

[FltReferenceFileNameInformation](nf-fltkernel-fltreferencefilenameinformation.md)

[FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md)

[IoGetTopLevelIrp](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp)

[PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)

[PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)
