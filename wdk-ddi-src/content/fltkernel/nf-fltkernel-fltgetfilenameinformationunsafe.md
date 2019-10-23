---
UID: NF:fltkernel.FltGetFileNameInformationUnsafe
title: FltGetFileNameInformationUnsafe function (fltkernel.h)
description: The FltGetFileNameInformationUnsafe routine returns name information for an open file or directory.
old-location: ifsk\fltgetfilenameinformationunsafe.htm
tech.root: ifsk
ms.assetid: 3c5ec515-d332-4fef-8b78-b2f04a672fd7
ms.date: 05/09/2019
ms.keywords: FltGetFileNameInformationUnsafe, FltGetFileNameInformationUnsafe routine [Installable File System Drivers], fltkernel/FltGetFileNameInformationUnsafe, ifsk.fltgetfilenameinformationunsafe
ms.topic: function
f1_keywords:
 - "fltkernel/FltGetFileNameInformationUnsafe"
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
req.irql: <= APC_LEVEL (see Remarks)
topic_type:
- APIRef
- kbSyntax
api_type:
- DllExport
api_location:
- fltmgr.sys
api_name:
- FltGetFileNameInformationUnsafe
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetFileNameInformationUnsafe function

## -description

The **FltGetFileNameInformationUnsafe** routine returns name information for an open file or directory.

## -parameters

### -param FileObject [in]

Pointer to a file object for the file or directory. The file object must be currently open. This parameter is required and cannot be set to **NULL**.

### -param Instance [in, optional]

Instance pointer for the caller. This parameter can be set to **NULL**.

### -param NameOptions [in]

A [FLT_FILE_NAME_OPTIONS](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options) value containing flags that specify the format of the name information to be returned, as well as the query method to be used by the Filter Manager. This parameter is required and cannot be set to **NULL**.

The following table describes the name format flag values. Only one of the flags can be specified. For more information about these formats, see [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md).

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_NORMALIZED

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the normalized name for the file.

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_OPENED

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the name that was used when the file was opened.

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_SHORT

</td>
<td>
The <i>FileNameInformation</i> parameter receives the address of a structure containing the short (8.3) name for the file. The short name consists of up to 8 characters, followed immediately by a period and up to 3 more characters. The short name for a file does not include the volume name, directory path, or stream name.

</td>
</tr>
</table>

The following table describes the query method flag values. Only one of the flags can be specified.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_DEFAULT

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, <b>FltGetFileNameInformationUnsafe</b> queries the file system and caches the result.

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_CACHE_ONLY

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. <b>FltGetFileNameInformationUnsafe</b> does not query the file system.

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_FILESYSTEM_ONLY

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the file system for the file name information. <b>FltGetFileNameInformationUnsafe</b> does not query the Filter Manager's name cache, and does not cache the result of the file system query.

</td>
</tr>
<tr>
<td>
FLT_FILE_NAME_QUERY_ALWAYS_ALLOW_CACHE_LOOKUP

</td>
<td>
<b>FltGetFileNameInformationUnsafe</b> queries the Filter Manager's name cache for the file name information. If the name is not found in the cache, and it is currently safe to do so, <b>FltGetFileNameInformationUnsafe</b> queries the file system for the file name information and caches the result.

</td>
</tr>
</table>

### -param FileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a system-allocated FLT_FILE_NAME_INFORMATION structure. **FltGetFileNameInformationUnsafe** allocates this structure from paged pool. When this information is no longer needed, the caller must release the structure by calling [FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md). This parameter is required and cannot be set to **NULL**.

## -returns

**FltGetFileNameInformationUnsafe** returns STATUS_SUCCESS or an appropriate NTSTATUS value such as one of the following:

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
The file object that the <i>FileObject</i> parameter points to is not currently open. This is an error code.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt><b>STATUS_INVALID_PARAMETER</b></dt>
</dl>
</td>
<td width="60%">
An invalid value was passed for the <i>FileNameInformation</i> parameter. This is an error code.

</td>
</tr>
</table>

## -remarks

The **FltGetFileNameInformationUnsafe** routine is provided so that you can query the name of a file object outside of the context of an I/O operation on that file object; otherwise, you must call [FltGetFileNameInformation](nf-fltkernel-fltgetfilenameinformation.md).

Unlike the **FltGetFileNameInformation** routine, **FltGetFileNameInformationUnsafe** does not protect the caller against the following types of circumstances, where querying the file system for name information can cause deadlocks for query methods other than FLT_FILE_NAME_QUERY_CACHE_ONLY:

* In the paging I/O path.

* When the **TopLevelIrp** field of the current thread is not **NULL**. For more information, see [IoGetTopLevelIrp](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp).

* After an [IRP_MJ_CLEANUP](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup) operation is completed; that is, in the post-clean up, pre-close, or post-close path (the target file object has the FO_CLEANUP_COMPLETE flag set).

* In a preoperation ([PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)) or postoperation ([PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)) callback routine for any of the following operations:

  * IRP_MJ_ACQUIRE_FOR_CC_FLUSH
  * IRP_MJ_ACQUIRE_FOR_MOD_WRITE
  * IRP_MJ_RELEASE_FOR_CC_FLUSH
  * IRP_MJ_RELEASE_FOR_MOD_WRITE
  * IRP_MJ_RELEASE_FOR_SECTION_SYNCHRONIZATION

* In a postoperation callback routine for IRP_MJ_ACQUIRE_FOR_SECTION_SYNCHRONIZATION.

* When all APCs are disabled; that is, when [KeAreAllApcsDisabled](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nf-wdm-keareallapcsdisabled) returns TRUE.

For Windows Vista / Server 2008 and later, if a minifilter does not yet have a filter instance, such as in its [DriverEntry](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/nc-wdm-driver_initialize) routine, it can use `NULL` for the *Instance* parameter. This allows *DriverEntry* routines to access file name information. Except for this case, a `NULL` value for the instance parameter is reserved for system use.

In create, hard-link, and rename operations, file name tunneling can invalidate the final component in normalized file name information that a minifilter driver retrieves in a preoperation callback routine. If a minifilter driver retrieves normalized file name information in a preoperation callback ([PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)) routine by calling a routine such as **FltGetFileNameInformationUnsafe**, it must call [FltGetTunneledName](nf-fltkernel-fltgettunneledname.md) from its postoperation callback ([PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)) routine to retrieve the correct file name information for the file.

For more information about normalized file name information, see [FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md).

## -see-also

[FLT_FILE_NAME_INFORMATION](ns-fltkernel-_flt_file_name_information.md)

<a href="https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-file-name-options">FLT_FILE_NAME_OPTIONS</a>

[FltGetDestinationFileNameInformation](nf-fltkernel-fltgetdestinationfilenameinformation.md)

[FltGetFileNameInformation](nf-fltkernel-fltgetfilenameinformation.md)

[FltGetTunneledName](nf-fltkernel-fltgettunneledname.md)

[FltReferenceFileNameInformation](nf-fltkernel-fltreferencefilenameinformation.md)

[FltReleaseFileNameInformation](nf-fltkernel-fltreleasefilenameinformation.md)

[IRP_MJ_CLEANUP](https://docs.microsoft.com/windows-hardware/drivers/ifs/irp-mj-cleanup)

[IoGetTopLevelIrp](https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/nf-ntifs-iogettoplevelirp)

[PFLT_POST_OPERATION_CALLBACK](nc-fltkernel-pflt_post_operation_callback.md)

[PFLT_PRE_OPERATION_CALLBACK](nc-fltkernel-pflt_pre_operation_callback.md)
