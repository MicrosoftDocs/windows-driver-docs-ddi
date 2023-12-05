---
UID: NF:fltkernel.FltGetDestinationFileNameInformation
title: FltGetDestinationFileNameInformation function (fltkernel.h)
description: Learn more about the FltGetDestinationFileNameInformation routine.
tech.root: ifsk
ms.date: 12/04/2023
keywords: ["FltGetDestinationFileNameInformation function"]
ms.keywords: FltApiRef_e_to_o_127cb786-b74b-4c1b-bb38-87ad3494900b.xml, FltGetDestinationFileNameInformation, FltGetDestinationFileNameInformation routine [Installable File System Drivers], fltkernel/FltGetDestinationFileNameInformation, ifsk.fltgetdestinationfilenameinformation
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
targetos: Windows
req.typenames: 
f1_keywords:
 - FltGetDestinationFileNameInformation
 - fltkernel/FltGetDestinationFileNameInformation
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - fltmgr.sys
api_name:
 - FltGetDestinationFileNameInformation
---

# FltGetDestinationFileNameInformation function

## -description

The **FltGetDestinationFileNameInformation** routine queries the file name for the destination's parent directory, then constructs a full destination path name for a file or directory that is being renamed or for which an NTFS hard link is being created.

## -parameters

### -param Instance [in]

Opaque instance pointer for a minifilter driver instance that is attached to the volume where the file resides.

### -param FileObject [in]

Pointer to the file object for the file. This parameter is required and can't be NULL.

### -param RootDirectory [in, optional]

*For link operations:* If the link is to be created in the same directory as the file that is being linked to or if **FileName** contains the full pathname for the link to be created, this parameter is NULL. Otherwise it's a handle for the directory where the link is to be created.

*For rename operations:* If the file isn't being moved to a different directory or if **FileName** contains the full pathname, this parameter is NULL. Otherwise it's a handle for the directory where the file resides after it's renamed.

### -param FileName [in]

*For link operations:* Pointer to a wide-character string containing the name to be assigned to the newly created link.

*For rename operations:* Pointer to a wide-character string containing the new name for the file.

### -param FileNameLength [in]

Length, in bytes, of the wide-character string that **FileName** points to.

### -param NameOptions [in]

A [**FLT_FILE_NAME_OPTIONS**](/windows-hardware/drivers/ifs/flt-file-name-options) value containing flags that specify the format of the name information to be returned, the query method that the Filter Manager is to use, and additional file name flags. This parameter is required and can't be NULL.

The following are the name format flag values. Only one name format flag can be specified. (Note that FLT_FILE_NAME_SHORT isn't a valid flag value for this parameter.)

| Name Format Flag Value | Meaning |
| ---------------------- | ------- |
| FLT_FILE_NAME_NORMALIZED | The **FileName** parameter receives the normalized destination name for the file. |
| FLT_FILE_NAME_OPENED | The **FileName** parameter receives the destination name for the file, based on the name that was used when the file was opened. This file name isn't normalized. |

The following are the query method flag values. Only one query method flag can be specified.

| Query Method Flag Value | Meaning |
| ----------------------- | ------- |
| FLT_FILE_NAME_QUERY_DEFAULT | If it isn't currently safe to query the file system for the destination file name, **FltGetDestinationFileNameInformation** does nothing. Otherwise, **FltGetDestinationFileNameInformation** queries the Filter Manager's name cache for the file name information for the destination's parent directory then appends the destination name. If the resultant name isn't found in the cache, **FltGetDestinationFileNameInformation** queries the file system and caches the result. |
| FLT_FILE_NAME_QUERY_CACHE_ONLY | **FltGetDestinationFileNameInformation** queries the Filter Manager's name cache for the file name information for the destination's parent directory then appends the destination name. It doesn't query the file system. |
| FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY | **FltGetDestinationFileNameInformation** queries the file system for the file name information for the destination's parent directory then appends the destination name. It doesn't query the Filter Manager's name cache and doesn't cache the result of the file system query. |
| FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP | **FltGetDestinationFileNameInformation** queries the Filter Manager's name cache for the file name information for the destination's parent directory then appends the destination name. If the name isn't found in the cache, and it's currently safe to do so, **FltGetDestinationFileNameInformation** queries the file system for the file name information and caches the result. |

The following are the file name flag values. Any combination of these flags can be specified. (Note that FLT_FILE_NAME_ALLOW_QUERY_ON_REPARSE isn't a relevant flag for this parameter since **FltGetDestinationFileNameInformation** isn't used in a post-create callback.)

| File Name Flag Value | Meaning |
| ----------------------- | ------- |
| FLT_FILE_NAME_REQUEST_FROM_CURRENT_PROVIDER | **FltGetDestinationFileNameInformation** directs the name request to the calling filter instance to complete. |
| FLT_FILE_NAME_DO_NOT_CACHE | **FltGetDestinationFileNameInformation** doesn't cache the retrieved file name. Name provider minifilters use this flag as they perform intermediate queries to generate a name. |

### -param RetFileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a system-allocated [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md) structure containing the file name information. **FltGetDestinationFileNameInformation** allocates this structure from paged pool. This parameter is required and can't be NULL.

## -returns

**FltGetDestinationFileNameInformation** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

| Return code | Description |
| ----------- | ----------- |
| STATUS_FLT_INVALID_NAME_REQUEST | This value is returned for either of the following reasons: (1) **FltGetDestinationFileNameInformation** can't get file name information if the **TopLevelIrp** field of the current thread isn't NULL, because the [resulting file system recursion could cause deadlocks or stack overflows](../ntifs/nf-ntifs-iogettoplevelirp.md). (2) **FLT_FILE_NAME_SHORT** was specified for the name format flag in the **NameOptions** parameter. |
| STATUS_INSUFFICIENT_RESOURCES   | **FltGetDestinationFileNameInformation** encountered a pool allocation failure. This is an error code. |
| STATUS_INVALID_PARAMETER        | An invalid value was specified for the **NameOptions** parameter. This is an error code. |
| STATUS_MOUNT_POINT_NOT_RESOLVED | The destination path name contains a mount point that resolves to a volume other than the one where the file resides. (Because a rename or hard-link-creation operation can only be performed within a volume and not across volumes, the operation fails.) This is an error code. |

## -remarks

Minifilters typically call **FltGetDestinationFileNameInformation** in a [preoperation callback routine](nc-fltkernel-pflt_pre_operation_callback.md) for a rename or hard-link-creation operation, which means that the destination file name most likely doesn't exist. The "destination" name is:

* For a file rename, the name the file will have if the rename succeeds. For example, when renaming *name1* to *name2*, *name2* is the destination name.
* For a hard-link-creation operation, the name being added to the file system. For example, when adding the hard link *name2* to the existing file named *name1*, *name2* is the destination name.

**FltGetDestinationFileNameInformation** returns the destination file name information in either normalized or "opened file" format. For more information on these formats, see the [**FLT_FILE_NAME_INFORMATION**](ns-fltkernel-_flt_file_name_information.md) structure.

The file object pointer that is passed for the **FileObject** parameter must be either the **FileObject** member of the [**FLT_RELATED_OBJECTS**](ns-fltkernel-_flt_related_objects.md) structure for the operation or the **Data->Iopb->TargetFileObject** pointer for the operation, where **Data** is the callback data structure for the operation ([**FLT_CALLBACK_DATA**](ns-fltkernel-_flt_callback_data.md)). The file object pointer can't be the **Data->Iopb->Parameters.SetFileInformation.FileObject** member, because this field isn't used uniformly across file systems.

If the user opened the file by using the file ID but doesn't have traverse privilege for the entire path, **FltGetDestinationFileNameInformation** returns only the portion of the path that the user has privilege for.

A rename or hard-link-creation operation can only be performed within a volume and not across volumes. Therefore, such an operation fails if the destination path name contains a mount point that resolves to a volume other than the one where the file resides. For more information about rename operations, see the [FILE_RENAME_INFORMATION](../ntifs/ns-ntifs-_file_rename_information.md) structure. For more information about hard-link creation operations, see the [**FILE_LINK_INFORMATION**](../ntifs/ns-ntifs-_file_link_information.md) structures.

After a successful call to **FltGetDestinationFileNameInformation**, the caller is responsible for releasing the pointer returned in the **RetFileNameInformation** parameter when it's no longer needed by calling [**FltReleaseFileNameInformation**](nf-fltkernel-fltreleasefilenameinformation.md).

The caller must not modify the contents of the structure returned in the **RetFileNameInformation** parameter, because this structure is cached by the Filter Manager so that all minifilter drivers can use it.

In create, hard-link, and rename operations, file name tunneling can cause the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine to be invalidated. If a minifilter driver retrieves normalized file name information in a preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)) routine by calling a routine such as **FltGetDestinationFileNameInformation**, it must call [**FltGetTunneledName**](nf-fltkernel-fltgettunneledname.md) from its [postoperation callback](nc-fltkernel-pflt_post_operation_callback.md) routine to retrieve the correct file name information for the file.

For more information about normalized file name information, see [**FLT_FILE_NAME_INFORMATION**](ns-fltkernel-_flt_file_name_information.md).

File name tunneling affects only create, hard-link, and rename operations in this way. It doesn't affect other I/O operations, such as read and write.

The following paired operations can cause the file name *name* to be tunneled:

* delete(*name*)/create(*name*)
* delete(*name*)/rename(*source*, *name*)
* rename(*name*, *newname*)/create(*name*)
* rename(*name*, *newname*)/rename(*source*, *name*)

## -see-also

[FILE_RENAME_INFORMATION](../ntifs/ns-ntifs-_file_rename_information.md)

[FILE_LINK_INFORMATION](../ntifs/ns-ntifs-_file_link_information.md)

[FLT_CALLBACK_DATA](ns-fltkernel-_flt_callback_data.md)

[FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md)

[FLT_FILE_NAME_OPTIONS](/windows-hardware/drivers/ifs/flt-file-name-options)

[FLT_RELATED_OBJECTS](ns-fltkernel-_flt_related_objects.md)

[FltGetFileNameInformation](nf-fltkernel-fltgetfilenameinformation.md)

[FltGetFileNameInformationUnsafe](nf-fltkernel-fltgetfilenameinformationunsafe.md)

[FltGetTunneledName](nf-fltkernel-fltgettunneledname.md)

[FltParseFileNameInformation](nf-fltkernel-fltparsefilenameinformation.md)

[FltReferenceFileNameInformation](nf-fltkernel-fltreferencefilenameinformation.md)

[FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md)

[IoGetTopLevelIrp](../ntifs/nf-ntifs-iogettoplevelirp.md)

[PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)

[PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)
