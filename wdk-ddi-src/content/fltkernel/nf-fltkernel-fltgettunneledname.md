---
UID: NF:fltkernel.FltGetTunneledName
title: FltGetTunneledName function (fltkernel.h)
description: The FltGetTunneledName routine retrieves the tunneled name for a file, given the normalized name returned for the file by a previous call to FltGetFileNameInformation, FltGetFileNameInformationUnsafe, or FltGetDestinationFileNameInformation.
old-location: ifsk\fltgettunneledname.htm
tech.root: ifsk
ms.assetid: 760ee574-5ca5-4db1-8b47-009a12398076
ms.date: 06/27/2019
keywords: ["FltGetTunneledName function"]
ms.keywords: FltApiRef_e_to_o_5a952e3d-25d1-48e7-b91b-9891a446d53b.xml, FltGetTunneledName, FltGetTunneledName routine [Installable File System Drivers], fltkernel/FltGetTunneledName, ifsk.fltgettunneledname
f1_keywords:
 - "fltkernel/FltGetTunneledName"
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
- FltGetTunneledName
product:
- Windows
targetos: Windows
req.typenames: 
---

# FltGetTunneledName function

## -description

The **FltGetTunneledName** routine retrieves the tunneled name for a file, given the normalized name returned for the file by a previous call to [**FltGetFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation), [**FltGetFileNameInformationUnsafe**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe), or [**FltGetDestinationFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation).

## -parameters

### -param CallbackData [in]

Pointer to the callback data structure for the I/O operation ([FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)). This parameter is required and cannot be **NULL**.

### -param FileNameInformation [in]

Pointer to an [FLT_FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information) structure containing normalized name information returned by a previous call to [**FltGetFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation), [**FltGetFileNameInformationUnsafe**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe), or [**FltGetDestinationFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation) for the file.

### -param RetTunneledFileNameInformation [out]

Pointer to a caller-allocated variable that receives the address of a newly allocated structure containing the tunneled file name. If no tunneled name is found, this variable receives **NULL**. This parameter is required and cannot be **NULL** on input.

## -returns

**FltGetTunneledName** returns STATUS_SUCCESS if the tunneled name is found or if there is no tunneled name for the file. Otherwise, it returns an NTSTATUS value, such as the following:

| Return code | Description |
| ----------- | ----------- |
| **STATUS_INSUFFICIENT_RESOURCES** | **FltGetTunneledName** encountered a pool allocation failure. This is an error code. |

## -remarks

File systems, such as NTFS and FAT, use a per-volume tunnel cache to briefly preserve file names and other metadata for files that are being renamed, linked to, or deleted. File name tunneling can cause the final component in normalized file name information returned by a preoperation call to [**FltGetFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation), [**FltGetFileNameInformationUnsafe**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe), or [**FltGetDestinationFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation) to be invalidated.

If a minifilter driver retrieves normalized file name information in the preoperation callback routine ([PFLT_PRE_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback)) for a create (IRP_MJ_CREATE), hard-link (IRP_MJ_SET_INFORMATION with [FILE_INFORMATION_CLASS](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ne-wdm-_file_information_class) set to *FileRenameInformation*), or rename operation (IRP_MJ_SET_INFORMATION with FILE_INFORMATION_CLASS set to *FileLinkInformation*), it must call **FltGetTunneledName** from its postoperation callback routine ([PFLT_POST_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback)) to retrieve the correct file name information for the file.

Only normalized file name information is affected by tunneling. The Filter Manager cannot ensure that the final component is normalized until after the create, hard-link, or rename operation has actually occurred, because tunneling can cause a short name to be changed to a long name. Thus a minifilter driver must call **FltGetTunneledName** from its postoperation callback routine to determine whether the normalized file name information retrieved in the preoperation callback routine is valid.

For more information about normalized file name information, see [FLT_FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information).

Minifilter drivers that only retrieve short or opened file name information should not call **FltGetTunneledName**.

After calling **FltGetFileNameInformation**, **FltGetFileNameInformationUnsafe**, or **FltGetDestinationFileNameInformation** in the preoperation callback routine, the minifilter driver must store the returned *FileNameInformation* pointer in the preoperation callback routine's *CompletionContext* structure so that the postoperation callback can pass this pointer in the *FileNameInformation* parameter to **FltGetTunneledName**.

> [!NOTE]
> File name tunneling affects only create, hard-link, and rename operations in this way. It does not affect other I/O operations, such as read and write.

The following paired operations can cause the file name *name* to be tunneled:

* delete(*name*)/create(*name*)
* delete(*name*)/rename(*source*, *name*)
* rename(*name*, *newname*)/create(*name*)
* rename(*name*, *newname*)/rename(*source*, *name*)

If no tunneled name is found for the file, the *RetTunneledFileNameInformation* parameter receives **NULL**.

After a successful call to **FltGetTunneledName**, the caller is responsible for releasing the *RetTunneledFileNameInformation* and *FileNameInformation* pointers when they are no longer needed by calling [**FltReleaseFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasefilenameinformation).

**FltGetTunneledName** should only be called from a minifilter driver's postoperation callback routine for IRP_MJ_CREATE or IRP_MJ_SET_INFORMATION. Calling **FltGetTunneledName** from a postoperation callback routine for any other type of I/O operation, or calling it from a preoperation callback routine, is a programming error.

The caller must not modify the contents of the structure returned in the *RetTunneledFileNameInformation* parameter, because this structure is cached by the Filter Manager so that all minifilter drivers can use it.

File tunneling enables compatibility with programs that rely on file systems to preserve file meta-information for a short period of time; for example, for the safe save process. Tunneling preserves the association between a file's long and short (8.3) name. When a file name is removed from a directory (rename or delete), its short and long name pair and creation time are saved in a tunnel cache, keyed by the name that was removed. When a name is added to a directory (rename or create), the cache is searched to determine if there is information to restore. The cache is effective per instance of a directory. If a directory is deleted, its cache is removed.

## -see-also

[FLT_CALLBACK_DATA](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_callback_data)

[FLT_FILE_NAME_INFORMATION](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/ns-fltkernel-_flt_file_name_information)

[**FltGetDestinationFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetdestinationfilenameinformation)

[**FltGetFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformation)

[**FltGetFileNameInformationUnsafe**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltgetfilenameinformationunsafe)

[**FltParseFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltparsefilenameinformation)

[**FltReferenceFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreferencefilenameinformation)

[**FltReleaseFileNameInformation**](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltreleasefilenameinformation)

[PFLT_POST_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_post_operation_callback)

[PFLT_PRE_OPERATION_CALLBACK](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nc-fltkernel-pflt_pre_operation_callback)
