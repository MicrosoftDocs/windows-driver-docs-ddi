---
UID: NF:fltkernel.FltGetDestinationFileNameInformation
title: FltGetDestinationFileNameInformation function (fltkernel.h)
description: The FltGetDestinationFileNameInformation routine constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created.
old-location: ifsk\fltgetdestinationfilenameinformation.htm
tech.root: ifsk
ms.assetid: b5438802-fc96-4445-9261-5d497d2d24cc
ms.date: 05/22/2019
ms.keywords: FltApiRef_e_to_o_127cb786-b74b-4c1b-bb38-87ad3494900b.xml, FltGetDestinationFileNameInformation, FltGetDestinationFileNameInformation routine [Installable File System Drivers], fltkernel/FltGetDestinationFileNameInformation, ifsk.fltgetdestinationfilenameinformation
ms.topic: function
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
req.irql: <= APC_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetDestinationFileNameInformation
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetDestinationFileNameInformation function

## -description

The **FltGetDestinationFileNameInformation** routine constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created.

## -parameters

### -param Instance [in]

Opaque instance pointer for a minifilter driver instance that is attached to the volume where the file resides.

### -param FileObject [in]

Pointer to the file object for the file. This parameter is required and cannot be **NULL**.

### -param RootDirectory [in, optional]

**For link operations:** If the link is to be created in the same directory as the file that is being linked to, or if the *FileName* parameter contains the full pathname for the link to be created, this parameter is **NULL**. Otherwise it is a handle for the directory where the link is to be created.

**For rename operations:** If the file is not being moved to a different directory, or if the *FileName* parameter contains the full pathname, this parameter is **NULL**. Otherwise it is a handle for the directory where the file resides after it is renamed.

### -param FileName [in]

**Link operations:** Pointer to a wide-character string containing the name to be assigned to the newly created link.

**Rename operations:** Pointer to a wide-character string containing the new name for the file.

### -param FileNameLength [in]

Length, in bytes, of the wide-character string that *FileName* points to.

### -param NameOptions [in]

[FLT_FILE_NAME_OPTIONS](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options) value containing flags that specify the format of the name information to be returned, the query method that the Filter Manager is to use, and additional file name flags. This parameter is required and cannot be **NULL**.

The following are the name format flag values. Only one name format flag can be specified. (Note that FLT_FILE_NAME_SHORT is not a valid flag value for this parameter.)

| Name Format Flag Value | Meaning |
| ---------------------- | ------- |
| FLT_FILE_NAME_NORMALIZED | The *FileName* parameter receives the normalized destination name for the file. |
| FLT_FILE_NAME_OPENED | The *FileName* parameter receives the destination name for the file, based on the name that was used when the file was opened. This file name is not normalized. |

The following are the query method flag values. Only one query method flag can be specified.

| Query Method Flag Value | Meaning |
| ----------------------- | ------- |
| FLT_FILE_NAME_QUERY_DEFAULT | If it is not currently safe to query the file system for the file name, **FltGetDestinationFileNameInformation** does nothing. Otherwise, **FltGetDestinationFileNameInformation** queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, **FltGetDestinationFileNameInformation** queries the file system and caches the result. |
| FLT_FILE_NAME_QUERY_CACHE_ONLY | **FltGetDestinationFileNameInformation** queries the Filter Manager's name cache for the file name information; it does not query the file system. |
| FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY | **FltGetDestinationFileNameInformation** queries the file system for the file name information. It does not query the Filter Manager's name cache, and does not cache the result of the file system query. |
| FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP | **FltGetDestinationFileNameInformation** queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, and it is currently safe to do so, **FltGetDestinationFileNameInformation** queries the file system for the file name information and cache the result. |

The following are the file name flag values. Any combination of these flags can be specified.

| File Name Flag Value | Meaning |
| ----------------------- | ------- |
| FLT_FILE_NAME_REQUEST_FROM_CURRENT_PROVIDER | **FltGetDestinationFileNameInformation** directs the name request to the calling filter instance to complete. |
| FLT_FILE_NAME_DO_NOT_CACHE | **FltGetDestinationFileNameInformation** does not cache the retrieved file name. Name provider minifilters use this flag as they perform intermediate queries to generate a name. |
| FLT_FILE_NAME_ALLOW_QUERY_ON_REPARSE | Indicates that it is safe to query the name in the post-create path even if STATUS_REPARSE was returned. It is the caller's responsibility to ensure that the **FileObject->FileName** field was not changed. Do not use this flag with mount points or symbolic link reparse points. |

### -param RetFileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a system-allocated [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md) structure containing the file name information. **FltGetDestinationFileNameInformation** allocates this structure from paged pool. This parameter is required and cannot be **NULL**.

## -returns

**FltGetDestinationFileNameInformation** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

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
This return value means one of the following:
<ul>
<li>
<b>FltGetDestinationFileNameInformation</b> cannot get file name information if the <b>TopLevelIrp</b> field of the current thread is not <b>NULL</b>, because the resulting file system recursion could cause deadlocks or stack overflows. (For more information about this issue, see <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iogettoplevelirp" data-linktype="external">IoGetTopLevelIrp</a>.)
</li>
<li>
FLT_FILE_NAME_SHORT was specified for the name format flag in the <i>NameOptions</i> parameter.
</li>
</ul>
</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INSUFFICIENT_RESOURCES</b></dt>
</dl>
</td>
<td width="60%">
<b>FltGetDestinationFileNameInformation</b> encountered a pool allocation failure. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was specified for the <i>NameOptions</i> parameter. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_MOUNT_POINT_NOT_RESOLVED</b></dt>
</dl>
</td>
<td width="60%">
The destination path name contains a mount point that resolves to a volume other than the one where the file resides. (Because a rename or hard-link-creation operation can only be performed within a volume and not across volumes, the operation fails.) This is an error code.

</td>
</tr>
</table>

## -remarks

**FltGetDestinationFileNameInformation** returns the file name information in either normalized or "opened file" format. For more information on these formats, see the [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md) structure.

The file object pointer that is passed for the *FileObject* parameter must be either the **FileObject** member of the [FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md) structure for the operation or the **Data->Iopb->TargetFileObject** pointer for the operation, where **Data** is the callback data structure for the operation ([FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)). The file object pointer cannot be the **Data->Iopb->Parameters.SetFileInformation.FileObject** member, because this field is not used uniformly across file systems.

If the user opened the file by using the file ID but does not have traverse privilege for the entire path, **FltGetDestinationFileNameInformation** returns only the portion of the path that the user has privilege for.

A rename or hard-link-creation operation can only be performed within a volume and not across volumes. Therefore, such an operation fails if the destination path name contains a mount point that resolves to a volume other than the one where the file resides. For more information about rename operations, see the [FILE_RENAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_rename_information) structure. For more information about hard-link creation operations, see the [FILE_LINK_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_link_information) structures.

After a successful call to **FltGetDestinationFileNameInformation**, the caller is responsible for releasing the pointer returned in the *RetFileNameInformation* parameter when it is no longer needed by calling [FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md).

The caller must not modify the contents of the structure returned in the *RetFileNameInformation* parameter, because this structure is cached by the Filter Manager so that all minifilter drivers can use it.

In create, hard-link, and rename operations, file name tunneling can cause the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine to be invalidated. If a minifilter driver retrieves normalized file name information in a preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)) routine by calling a routine such as **FltGetDestinationFileNameInformation**, it must call [FltGetTunneledName](nf-fltkernel-fltgettunneledname.md) from its postoperation callback ([PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)) routine to retrieve the correct file name information for the file.

For more information about normalized file name information, see [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md).

<div class="alert"><b>Note</b>    File name tunneling affects only create, hard-link, and rename operations in this way. It does not affect other I/O operations, such as read and write. </div>

The following paired operations can cause the file name *name* to be tunneled:

* delete(*name*)/create(*name*)
* delete(*name*)/rename(*source*, *name*)
* rename(*name*, *newname*)/create(*name*)
* rename(*name*, *newname*)/rename(*source*, *name*)

## -see-also

[FILE_RENAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_rename_information)

[FILE_LINK_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/ns-ntifs-_file_link_information)

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md)

[FLT_FILE_NAME_OPTIONS](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options)

[FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md)

[FltGetFileNameInformation](nf-fltkernel-fltgetfilenameinformation.md)

[FltGetFileNameInformationUnsafe](nf-fltkernel-fltgetfilenameinformationunsafe.md)

[FltGetTunneledName](nf-fltkernel-fltgettunneledname.md)

[FltParseFileNameInformation](nf-fltkernel-fltparsefilenameinformation.md)

[FltReferenceFileNameInformation](nf-fltkernel-fltreferencefilenameinformation.md)

[FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md)

[IoGetTopLevelIrp](https://docs.microsoft.com/windows-hardware/drivers/ddi/content/ntifs/nf-ntifs-iogettoplevelirp)

[PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)

[PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback)