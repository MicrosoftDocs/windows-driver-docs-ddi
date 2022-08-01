---
UID: NS:ntifs._REPARSE_GUID_DATA_BUFFER
title: REPARSE_GUID_DATA_BUFFER (ntifs.h)
description: The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point.
old-location: ifsk\reparse_guid_data_buffer.htm
tech.root: ifsk
ms.date: 07/26/2022
keywords: ["REPARSE_GUID_DATA_BUFFER structure"]
ms.keywords: "*PREPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER, PREPARSE_GUID_DATA_BUFFER structure pointer [Installable File System Drivers], REPARSE_GUID_DATA_BUFFER, REPARSE_GUID_DATA_BUFFER structure [Installable File System Drivers], _REPARSE_GUID_DATA_BUFFER, fileinformationstructures_d020fad8-2a4b-4fe6-a1ca-bbf7575418b5.xml, ifsk.reparse_guid_data_buffer, ntifs/PREPARSE_GUID_DATA_BUFFER, ntifs/REPARSE_GUID_DATA_BUFFER"
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
targetos: Windows
req.typenames: REPARSE_GUID_DATA_BUFFER, *PREPARSE_GUID_DATA_BUFFER
f1_keywords:
 - _REPARSE_GUID_DATA_BUFFER
 - ntifs/_REPARSE_GUID_DATA_BUFFER
 - PREPARSE_GUID_DATA_BUFFER
 - ntifs/PREPARSE_GUID_DATA_BUFFER
 - REPARSE_GUID_DATA_BUFFER
 - ntifs/REPARSE_GUID_DATA_BUFFER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - _REPARSE_GUID_DATA_BUFFER
 - PREPARSE_GUID_DATA_BUFFER
 - REPARSE_GUID_DATA_BUFFER
---

# REPARSE_GUID_DATA_BUFFER structure

## -description

The REPARSE_GUID_DATA_BUFFER structure contains reparse point data for a reparse point.

## -struct-fields

### -field ReparseTag

Reparse point tag that uniquely identifies the owner of the reparse point. (See the following **Remarks** section.)

### -field ReparseDataLength

Size, in bytes, of the reparse data in the **DataBuffer** member.

### -field Reserved

Reserved; do not use.

### -field ReparseGuid

GUID that uniquely identifies the owner of the reparse point. (See the following **Remarks** section.)

### -field GenericReparseBuffer

### -field GenericReparseBuffer.DataBuffer

User-defined data for the reparse point. The format of this data is defined by the owner of the reparse point.

## -remarks

The REPARSE_GUID_DATA_BUFFER structure is used by all third-party file systems, filters, and minifilters, as well as some Microsoft file systems, filters, and minifilters to store data for a reparse point. Each reparse point contains one REPARSE_GUID_DATA_BUFFER structure.

Microsoft reparse points can use the [REPARSE_DATA_BUFFER](ns-ntifs-_reparse_data_buffer.md) structure instead of the REPARSE_GUID_DATA_BUFFER structure. However, third-party reparse points are required to use the REPARSE_GUID_DATA_BUFFER structure.

Reparse point tags are [assigned to third parties by Microsoft](/windows-hardware/drivers/ifs/reparse-point-tag-request). You may request more than one reparse point for use with a file system, file system filter driver, or minifilter driver.

Reparse point GUIDs are not assigned by Microsoft. However, you must choose one GUID to use with your assigned reparse point tag, and you must always use this GUID with the tag. To generate a GUID, you can use GUIDGen (*Guidgen.exe*), a tool that is included in the Microsoft Windows SDK.

Minifilters can set or delete a reparse point by calling [FltTagFile](../fltkernel/nf-fltkernel-flttagfile.md) or [FltUntagFile](../fltkernel/nf-fltkernel-fltuntagfile.md). Minifilters can retrieve a reparse point by using the [FSCTL_GET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-get-reparse-point) control code. This code can be sent to the file system by calling [FltFsControlFile](../fltkernel/nf-fltkernel-fltfscontrolfile.md).

File systems and filter drivers can retrieve, set, or delete a reparse point by using the [FSCTL_GET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-get-reparse-point), [FSCTL_SET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-set-reparse-point), and [FSCTL_DELETE_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-delete-reparse-point) control codes. These codes can be sent to the file system by calling [**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md).

For more information about reparse points and reparse point tags, see the Windows SDK documentation.

## -see-also

[FILE_REPARSE_POINT_INFORMATION](ns-ntifs-_file_reparse_point_information.md)

[FLT_PARAMETERS for IRP_MJ_FILE_SYSTEM_CONTROL](/windows-hardware/drivers/ifs/flt-parameters-for-irp-mj-file-system-control)

[FSCTL_DELETE_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-delete-reparse-point)

[FSCTL_GET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-get-reparse-point)

[FSCTL_SET_REPARSE_POINT](/windows-hardware/drivers/ifs/fsctl-set-reparse-point)

[FltFsControlFile](../fltkernel/nf-fltkernel-fltfscontrolfile.md)

[FltTagFile](../fltkernel/nf-fltkernel-flttagfile.md)

[FltTagFileEx](../fltkernel/nf-fltkernel-flttagfileex.md)

[FltUntagFile](../fltkernel/nf-fltkernel-fltuntagfile.md)

[IRP_MJ_FILE_SYSTEM_CONTROL](/windows-hardware/drivers/kernel/irp-mj-file-system-control)

[IsReparseTagMicrosoft](nf-ntifs-isreparsetagmicrosoft.md)

[IsReparseTagNameSurrogate](nf-ntifs-isreparsetagnamesurrogate.md)

[REPARSE_DATA_BUFFER](ns-ntifs-_reparse_data_buffer.md)

[REPARSE_DATA_BUFFER_EX](ns-ntifs-_reparse_data_buffer_ex.md)

[**ZwFsControlFile**](nf-ntifs-zwfscontrolfile.md)
