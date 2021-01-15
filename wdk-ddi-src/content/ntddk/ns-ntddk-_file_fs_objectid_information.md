---
UID: NS:ntddk._FILE_FS_OBJECTID_INFORMATION
title: _FILE_FS_OBJECTID_INFORMATION (ntddk.h)
description: The FILE_FS_OBJECTID_INFORMATION structure is used to query or set the object ID for a file system volume.
old-location: ifsk\file_fs_objectid_information.htm
tech.root: ifsk
ms.date: 07/12/2018
keywords: ["FILE_FS_OBJECTID_INFORMATION structure"]
ms.keywords: "*PFILE_FS_OBJECTID_INFORMATION, FILE_FS_OBJECTID_INFORMATION, FILE_FS_OBJECTID_INFORMATION structure [Installable File System Drivers], PFILE_FS_OBJECTID_INFORMATION, PFILE_FS_OBJECTID_INFORMATION structure pointer [Installable File System Drivers], _FILE_FS_OBJECTID_INFORMATION, fileinformationstructures_6a17f2c2-0aae-44a7-a65c-02c1ed2a9ed4.xml, ifsk.file_fs_objectid_information, ntddk/FILE_FS_OBJECTID_INFORMATION, ntddk/PFILE_FS_OBJECTID_INFORMATION"
req.header: ntddk.h
req.include-header: Ntddk.h, Ntifs.h, Fltkernel.h
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
req.typenames: FILE_FS_OBJECTID_INFORMATION, *PFILE_FS_OBJECTID_INFORMATION
f1_keywords:
 - _FILE_FS_OBJECTID_INFORMATION
 - ntddk/_FILE_FS_OBJECTID_INFORMATION
 - PFILE_FS_OBJECTID_INFORMATION
 - ntddk/PFILE_FS_OBJECTID_INFORMATION
 - FILE_FS_OBJECTID_INFORMATION
 - ntddk/FILE_FS_OBJECTID_INFORMATION
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntddk.h
api_name:
 - _FILE_FS_OBJECTID_INFORMATION
 - PFILE_FS_OBJECTID_INFORMATION
 - FILE_FS_OBJECTID_INFORMATION
---

# _FILE_FS_OBJECTID_INFORMATION structure


## -description

The FILE_FS_OBJECTID_INFORMATION structure is used to query or set the object ID for a file system volume.

## -struct-fields

### -field ObjectId

A 16-byte GUID that identifies the file system volume on the disk.

### -field ExtendedInfo

A 48-byte value containing optional, additional caller-defined information on the file system volume. The meaning of this extended information is opaque to the file system.

## -remarks

This information can be queried in either of the following ways:

* Call [**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md) or [**ZwQueryVolumeInformationFile**](./nf-ntddk-zwqueryvolumeinformationfile.md
), passing FileFsObjectIdInformation as the value of *FileInformationClass* and passing a caller-allocated, FILE_FS_OBJECTID_INFORMATION-structured buffer as the value of *FileInformation*.
* Create an IRP with major function code IRP_MJ_QUERY_VOLUME_INFORMATION.

No specific access rights are required to query this information. Thus this information is available as long as the volume is accessed through an open handle to the volume itself, or to a file or directory on the volume.

This information can be set in either of the following ways:

* Call [**FltSetVolumeInformation**](../fltkernel/nf-fltkernel-fltsetvolumeinformation.md) or [**ZwSetVolumeInformationFile**](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwsetvolumeinformationfile
), passing FileFsObjectIdInformation as the value of *FileInformationClass* and passing a caller-allocated, FILE_FS_OBJECTID_INFORMATION-structured buffer as the value of *FileInformation*.
* Create an IRP with major function code IRP_MJ_SET_VOLUME_INFORMATION.

FILE_WRITE_DATA access to the volume is required to set this information.

Support for volume object IDs is file-system-specific. In NTFS, volume object IDs are used extensively by the distributed link tracking service.

It is important to note that the volume object ID is not the same as the volume GUID. The *volume object ID* is assigned to the file system volume by the file system. The *volume GUID*, or *unique volume name*, is file system-independent; it is assigned to the underlying storage volume by the Volume Mount Manager.

To get the volume GUID for a volume, use the Win32 [**GetVolumeNameForVolumeMountPointW**](/windows/win32/api/fileapi/nf-fileapi-getvolumenameforvolumemountpointw) function or the [**FltGetVolumeGuidName**](../fltkernel/nf-fltkernel-fltgetvolumeguidname.md) routine.

The size of the buffer passed in the *FileInformation* parameter to **FltQueryVolumeInformation**, **FltSetVolumeInformation**, **ZwQueryVolumeInformationFile**, or **ZwSetVolumeInformationFile** must be at least **sizeof** (FILE_FS_OBJECTID_INFORMATION).

This structure must be aligned on a LONGLONG (8-byte) boundary.

## -see-also

[**FltGetVolumeGuidName**](../fltkernel/nf-fltkernel-fltgetvolumeguidname.md)

[**FltQueryVolumeInformation**](../fltkernel/nf-fltkernel-fltqueryvolumeinformation.md)

[**FltSetVolumeInformation**](../fltkernel/nf-fltkernel-fltsetvolumeinformation.md)

[**IRP_MJ_QUERY_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-volume-information)

[**IRP_MJ_SET_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-volume-information)

[**ZwQueryVolumeInformationFile**](./nf-ntddk-zwqueryvolumeinformationfile.md
)

[**ZwSetVolumeInformationFile**](/windows-hardware/drivers/ddi/ntddk/nf-ntddk-zwsetvolumeinformationfile
)

