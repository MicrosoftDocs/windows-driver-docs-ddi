---
UID: NS:ntifs._REPARSE_DATA_BUFFER
title: _REPARSE_DATA_BUFFER (ntifs.h)
description: The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point.
old-location: ifsk\reparse_data_buffer.htm
tech.root: ifsk
ms.assetid: e906a874-51f1-4623-8f0b-afdfd8169ab2
ms.date: 05/16/2019
keywords: ["REPARSE_DATA_BUFFER structure"]
ms.keywords: "*PREPARSE_DATA_BUFFER, PREPARSE_DATA_BUFFER, PREPARSE_DATA_BUFFER structure pointer [Installable File System Drivers], REPARSE_DATA_BUFFER, REPARSE_DATA_BUFFER structure [Installable File System Drivers], _REPARSE_DATA_BUFFER, fileinformationstructures_4f1b658e-1833-421f-a726-448b20b1c595.xml, ifsk.reparse_data_buffer, ntifs/PREPARSE_DATA_BUFFER, ntifs/REPARSE_DATA_BUFFER"
f1_keywords:
 - "ntifs/REPARSE_DATA_BUFFER"
 - "REPARSE_DATA_BUFFER"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntifs.h
api_name:
- REPARSE_DATA_BUFFER
targetos: Windows
req.typenames: REPARSE_DATA_BUFFER, *PREPARSE_DATA_BUFFER
---

# _REPARSE_DATA_BUFFER structure

## -description

The REPARSE_DATA_BUFFER structure contains reparse point data for a Microsoft reparse point. You can use [REPARSE_DATA_BUFFER_EX](ns-ntifs-_reparse_data_buffer_ex.md) instead. (Third-party reparse point owners must use the [REPARSE_GUID_DATA_BUFFER](ns-ntifs-_reparse_guid_data_buffer.md) structure instead.)

## -struct-fields

### -field ReparseTag

Reparse point tag. Must be a Microsoft reparse point tag. (See the following **Remarks** section.)

### -field ReparseDataLength

Size, in bytes, of the reparse data in the buffer that **DataBuffer** points to.

### -field Reserved

Length, in bytes, of the unparsed portion of the file name pointed to by the **FileName** member of the associated file object. For more information about the **FileName** member, see [FILE_OBJECT<](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object). This member is only valid for create operations when the I/O fails with STATUS_REPARSE. For all other purposes, such as setting or querying a reparse point for the reparse data, this member is treated as reserved.

### -field DUMMYUNIONNAME

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer.SubstituteNameOffset

Offset, in bytes, of the substitute name string in the **PathBuffer** array. Note that this offset must be divided by **sizeof**(WCHAR) to get the array index.

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer.SubstituteNameLength

Length, in bytes, of the substitute name string. If this string is NULL-terminated, **SubstituteNameLength** does not include space for the UNICODE_NULL terminator.

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer.PrintNameOffset

Offset, in bytes, of the print name string in the **PathBuffer** array. Note that this offset must be divided by **sizeof**(WCHAR) to get the array index.

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer.PrintNameLength

Length, in bytes, of the print name string. If this string is NULL-terminated, **PrintNameLength** does not include space for the UNICODE_NULL terminator.

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer.Flags

Indicates whether the symbolic link is absolute or relative.  If **Flags** contains SYMLINK_FLAG_RELATIVE, the symbolic link contained in the **PathBuffer** array (at offset **SubstituteNameOffset**) is processed as a relative symbolic link; otherwise, it is processed as an absolute symbolic link.

### -field DUMMYUNIONNAME.SymbolicLinkReparseBuffer.PathBuffer

First character of the path string. This character is followed in memory by the remainder of the string. The path string contains the substitute name string and print name string. The substitute name and print name strings can appear in any order in the **PathBuffer**. To locate the substitute name and print name strings in the **PathBuffer**, use the **SubstituteNameOffset**, **SubstituteNameLength**, **PrintNameOffset**, and **PrintNameLength** members.

### -field DUMMYUNIONNAME.MountPointReparseBuffer

### -field DUMMYUNIONNAME.MountPointReparseBuffer.SubstituteNameOffset

Offset, in bytes, of the substitute name string in the **PathBuffer** array. Note that this offset must be divided by **sizeof**(WCHAR) to get the array index.

### -field DUMMYUNIONNAME.MountPointReparseBuffer.SubstituteNameLength

Length, in bytes, of the substitute name string. If this string is NULL-terminated, **SubstituteNameLength** does not include space for the UNICODE_NULL terminator.

### -field DUMMYUNIONNAME.MountPointReparseBuffer.PrintNameOffset

Offset, in bytes, of the print name string in the **PathBuffer** array. Note that this offset must be divided by **sizeof**(WCHAR) to get the array index.

### -field DUMMYUNIONNAME.MountPointReparseBuffer.PrintNameLength

Length, in bytes, of the print name string. If this string is NULL-terminated, **PrintNameLength** does not include space for the UNICODE_NULL terminator.

### -field DUMMYUNIONNAME.MountPointReparseBuffer.PathBuffer

First character of the path string. This character is followed in memory by the remainder of the string. The path string contains the substitute name string and print name string. The substitute name and print name strings can appear in any order in the **PathBuffer**. To locate the substitute name and print name strings in the **PathBuffer**, use the **SubstituteNameOffset**, **SubstituteNameLength**, **PrintNameOffset**, and **PrintNameLength** members.

### -field DUMMYUNIONNAME.GenericReparseBuffer

### -field DUMMYUNIONNAME.GenericReparseBuffer.DataBuffer

Pointer to a buffer that contains Microsoft-defined data for the reparse point.

## -remarks

The REPARSE_DATA_BUFFER structure is used by Microsoft file systems, filters, and minifilter drivers, as well as the I/O manager, to store data for a reparse point.

This structure can only be used for Microsoft reparse points. Third-party reparse point owners must use the [REPARSE_GUID_DATA_BUFFER](ns-ntifs-_reparse_guid_data_buffer.md) structure instead.

Microsoft reparse points can use the REPARSE_DATA_BUFFER structure or the REPARSE_GUID_DATA_BUFFER structure.

From the union, you can use the GenericReparseBuffer structure to interpret the payload for any IO_REPARSE_TAG_XXX tag, or optionally use one of the other structures within the union as follows:

* Use the SymbolicLinkReparseBuffer structure when FileTag is IO_REPARSE_TAG_SYMLINK.

* Use the MountPointReparseBuffer structure when FileTag is IO_REPARSE_TAG_MOUNT_POINT.

For more information about reparse point tags, see the Microsoft Windows SDK documentation.

## -see-also

[FILE_OBJECT](https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_object)

[FILE_REPARSE_POINT_INFORMATION](ns-ntifs-_file_reparse_point_information.md)

[FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control)

[FSCTL_DELETE_REPARSE_POINT](https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-delete-reparse-point)

[FSCTL_GET_REPARSE_POINT](https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-get-reparse-point)

[FSCTL_SET_REPARSE_POINT](https://docs.microsoft.com/windows-hardware/drivers/ifs/fsctl-set-reparse-point)

[FltFsControlFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltfscontrolfile)

[FltTagFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfile)

[FltTagFileEx](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-flttagfileex)

[FltUntagFile](https://docs.microsoft.com/windows-hardware/drivers/ddi/fltkernel/nf-fltkernel-fltuntagfile)

[IRP_MJ_FILE_SYSTEM_CONTROL](https://docs.microsoft.com/windows-hardware/drivers/kernel/irp-mj-file-system-control)

[IsReparseTagMicrosoft](nf-ntifs-isreparsetagmicrosoft.md)

[IsReparseTagNameSurrogate](nf-ntifs-isreparsetagnamesurrogate.md)

[REPARSE_DATA_BUFFER_EX](ns-ntifs-_reparse_data_buffer_ex.md)

[REPARSE_GUID_DATA_BUFFER](ns-ntifs-_reparse_guid_data_buffer.md)

[ZwFsControlFile](https://msdn.microsoft.com/library/windows/hardware/ff566462)
