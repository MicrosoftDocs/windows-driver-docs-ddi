---
UID: NF:fltkernel.FltTagFileEx
title: FltTagFileEx function
description: FltTagFileEx sets a reparse flag on a file or directory.
tech.root: ifsk
ms.date: 03/12/2019
keywords: ["FltTagFileEx function"]
ms.keywords: FltTagFileEx, FltTagFile
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
 - FltTagFileEx
 - fltkernel/FltTagFileEx
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - fltkernel.h
api_name:
 - FltTagFileEx
---

# FltTagFileEx function


## -description

**FltTagFileEx** sets a reparse point on a file or directory.

## -parameters

### -param InitiatingInstance

Opaque pointer to the minifilter driver instance that initiated this I/O request. This parameter is required and cannot be **NULL**.

### -param FileObject

Pointer to the file object for the file or directory on which to set a reparse point. The file object must be opened for FILE_WRITE_DATA access. This parameter is required and cannot be **NULL**.

### -param FileTag

Reparse point tag. Can be one of the **IO_REPARSE_TAG_*XXX*** values defined in *ntifs.h*.

### -param Guid

GUID that uniquely identifies the reparse point. If *FileTag* is a non-Microsoft tag, this parameter is required and cannot be **NULL**. If an existing reparse tag is being modified, the GUID specified in this parameter must match the GUID of the reparse point to be modified.

### -param DataBuffer

Pointer to a buffer that contains user-defined data for the reparse point.

### -param DataBufferLength

Size, in bytes, of the buffer to which *DataBuffer* points.

### -param ExistingFileTag

Existing tag on the file if the tag has to be replaced. This parameter must be set to zero to set a reparse tag on a file that doesn't already have one.

### -param ExistingGuid

GUID that uniquely identifies an existing reparse point. If *ExistingFileTag* is a non-Microsoft tag and is non-zero, this parameter must not be **NULL**.

### -param Flags

Specifies the REPARSE_DATA_BUFFER_EX_*XXX* flags defined in *ntifs.h*.

## -returns

This function returns STATUS_SUCCESS or an appropriate NTSTATUS value such as the following:

| Return Code | Description |
| ----------- | ----------- |
| STATUS_IO_REPARSE_TAG_MISMATCH | The tag value specified in *ExistingFileTag* does not match that of the existing tag value. |
| STATUS_REPARSE_ATTRIBUTE_CONFLICT | For an existing reparse point with a non-Microsoft tag, *ExistingFileTag* matches the existing tag value, but the *Guid* does not match the existing Guid. |

## -remarks

Minifilter drivers should use **FltTagFileEx** instead of FSCTL_SET_REPARSE_POINT_EX to set a reparse point.

Not all file systems support reparse points; for example, the NTFS and ReFS file systems supports them, but the FAT file system does not. Minifilter drivers can determine whether a file system supports reparse points by calling [**FltQueryVolumeInformation**](nf-fltkernel-fltqueryvolumeinformation.md), specifying FileFsAttributeInformation for the *FsInformation* parameter, and examining the FILE_SUPPORTS_REPARSE_POINTS bit flag in the returned [FILE_FS_ATTRIBUTE_INFORMATION](../ntifs/ns-ntifs-_file_fs_attribute_information.md) structure.

To remove an existing reparse point, call [**FltUntagFile**](nf-fltkernel-fltuntagfile.md).

For more information about reparse points, see the Microsoft Windows SDK documentation.

## -see-also

[FILE_FS_ATTRIBUTE_INFORMATION](../ntifs/ns-ntifs-_file_fs_attribute_information.md)

[FLT_TAG_DATA_BUFFER](./ns-fltkernel-_flt_tag_data_buffer.md)

[FSCTL_DELETE_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-delete-reparse-point)

[FSCTL_GET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-get-reparse-point)

[FSCTL_SET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-set-reparse-point)

[**FltFsControlFile**](./nf-fltkernel-fltfscontrolfile.md)

[**FltQueryVolumeInformation**](./nf-fltkernel-fltqueryvolumeinformation.md)

[**FltTagFile**](./nf-fltkernel-flttagfile.md)

[**FltUntagFile**](./nf-fltkernel-fltuntagfile.md)

[**IsReparseTagMicrosoft**](../ntifs/nf-ntifs-isreparsetagmicrosoft.md)

[**IsReparseTagNameSurrogate**](../ntifs/nf-ntifs-isreparsetagnamesurrogate.md)

[REPARSE_DATA_BUFFER](../ntifs/ns-ntifs-_reparse_data_buffer.md)

[REPARSE_GUID_DATA_BUFFER](../ntifs/ns-ntifs-_reparse_guid_data_buffer.md)
