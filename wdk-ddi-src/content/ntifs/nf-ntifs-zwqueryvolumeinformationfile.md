---
UID: NF:ntifs.ZwQueryVolumeInformationFile
title: ZwQueryVolumeInformationFile function (ntifs.h)
description: Learn how the ZwQueryVolumeInformationFile routine retrieves information about the volume associated with a given file, directory, storage device, or volume.
old-location: kernel\zwqueryvolumeinformationfile.htm
tech.root: kernel
ms.date: 07/26/2022
keywords: ["ZwQueryVolumeInformationFile function"]
ms.keywords: NtQueryVolumeInformationFile, ZwQueryVolumeInformationFile, ZwQueryVolumeInformationFile routine [Kernel-Mode Driver Architecture], k111_1ca2c72d-6eb1-4bfa-a1f9-06cc26643662.xml, kernel.zwqueryvolumeinformationfile, ntifs/NtQueryVolumeInformationFile, ntifs/ZwQueryVolumeInformationFile
req.header: ntifs.h
req.include-header: Ntifs.h, Ntddk.h
req.target-type: Universal
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.ddi-compliance: PowerIrpDDis, HwStorPortProhibitedDDIs
req.unicode-ansi: 
req.idl: 
req.max-support: 
req.namespace: 
req.assembly: 
req.type-library: 
req.lib: NtosKrnl.lib
req.dll: NtosKrnl.exe
req.irql: PASSIVE_LEVEL (see Remarks section)
targetos: Windows
req.typenames: 
f1_keywords:
 - ZwQueryVolumeInformationFile
 - ntifs/ZwQueryVolumeInformationFile
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - DllExport
api_location:
 - NtosKrnl.exe
api_name:
 - ZwQueryVolumeInformationFile
---

# ZwQueryVolumeInformationFile function (ntifs.h)

## -description

The **ZwQueryVolumeInformationFile** routine retrieves information about the volume associated with a given file, directory, storage device, or volume.

## -parameters

### -param FileHandle [in]

A handle to a file object returned by [**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md) or [**ZwOpenFile**](../wdm/nf-wdm-zwopenfile.md) for an open file, directory, storage device, or volume for which volume information is being requested.

### -param IoStatusBlock [out]

A pointer to an [**IO_STATUS_BLOCK**](/windows-hardware/drivers/ddi/wdm/ns-wdm-_io_status_block) structure that receives the final completion status and information about the query operation. For successful calls that return data, the number of bytes written to the **FsInformation** buffer is returned in the structure's **Information** member.

### -param FsInformation [out]

A pointer to a caller-allocated buffer that receives the desired information about the volume. The structure of the information returned in the buffer is defined by the **FsInformationClass** parameter.

### -param Length [in]

Size in bytes of the buffer pointed to by **FsInformation**. The caller should set this parameter according to the given **FsInformationClass**.

### -param FsInformationClass [in]

Type of information to be returned about the volume. Set this member to one of the following [**FS_INFORMATION_CLASS**](../wdm/ne-wdm-_fsinfoclass.md) enumeration values.

| Value | Meaning |
| ----- | ------- |
| **FileFsAttributeInformation** | Return a [**FILE_FS_ATTRIBUTE_INFORMATION**](ns-ntifs-_file_fs_attribute_information.md) structure containing attribute information about the file system responsible for the volume. |
| **FileFsControlInformation** | Return a [**FILE_FS_CONTROL_INFORMATION**](ns-ntifs-_file_fs_control_information.md) structure containing file system control information about the volume. |
| **FileFsDeviceInformation** | Return a [**FILE_FS_DEVICE_INFORMATION**](../wdm/ns-wdm-_file_fs_device_information.md) structure containing device information for the volume. |
| **FileFsDriverPathInformation** | Return a [**FILE_FS_DRIVER_PATH_INFORMATION**](ns-ntifs-_file_fs_driver_path_information.md) structure containing information about whether a specified driver is in the I/O path for the volume. The caller must store the name of the driver into the **FILE_FS_DRIVER_PATH_INFORMATION** structure before calling **ZwQueryVolumeInformationFile**. |
| **FileFsFullSizeInformation** | Return a [**FILE_FS_FULL_SIZE_INFORMATION**](../ntddk/ns-ntddk-_file_fs_full_size_information.md) structure containing information about the total amount of space available on the volume. |
| **FileFsObjectIdInformation** | Return a [**FILE_FS_OBJECTID_INFORMATION**](../ntddk/ns-ntddk-_file_fs_objectid_information.md) structure containing file system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name assigned by the operating system. |
| **FileFsSizeInformation** | Return a [**FILE_FS_SIZE_INFORMATION**](../ntddk/ns-ntddk-_file_fs_size_information.md) structure containing information about the amount of space on the volume that is available to the user associated with the calling thread. |
| **FileFsVolumeInformation** | Return a [**FILE_FS_VOLUME_INFORMATION**](../ntddk/ns-ntddk-_file_fs_volume_information.md) containing information about the volume such as the volume label, serial number, and creation time. |
| **FileFsSectorSizeInformation** | Return a [**FILE_FS_SECTOR_SIZE_INFORMATION**](../ntddk/ns-ntddk-_file_fs_sector_size_information.md) structure that contains information about the physical and logical sector sizes of a volume. |

## -returns

**ZwQueryVolumeInformationFile** returns STATUS_SUCCESS or an appropriate error status.

## -remarks

**ZwQueryVolumeInformationFile** retrieves information about the volume associated with a given file, directory, storage device, or volume.

If the **FileHandle** represents a direct device open, only **FileFsDeviceInformation** can be specified as the value of **FsInformationClass**.

**ZwQueryVolumeInformationFile** returns zero in any member of a **FILE_**XXX**_INFORMATION** structure that is not supported by the file system.

For information about other file information query routines, see [File Objects](/windows-hardware/drivers/ddi/_kernel/#file-objects).

Minifilters should use [**FltQueryVolumeInformationFile**](../fltkernel/nf-fltkernel-fltqueryvolumeinformationfile.md) instead of **ZwQueryVolumeInformationFile**.

Callers of **ZwQueryVolumeInformationFile** must be running at IRQL = PASSIVE_LEVEL and [with special kernel APCs enabled](/windows-hardware/drivers/kernel/disabling-apcs).

> [!NOTE]
> If the call to the **ZwQueryVolumeInformationFile** function occurs in user mode, you should use the name "**NtQueryVolumeInformationFile**" instead of "**ZwQueryVolumeInformationFile**".

For calls from kernel-mode drivers, the **Nt*Xxx*** and **Zw*Xxx*** versions of a Windows Native System Services routine can behave differently in the way that they handle and interpret input parameters. For more information about the relationship between the **Nt*Xxx*** and **Zw*Xxx*** versions of a routine, see [Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines).

## -see-also

[**FILE_FS_ATTRIBUTE_INFORMATION**](ns-ntifs-_file_fs_attribute_information.md)

[**FILE_FS_CONTROL_INFORMATION**](ns-ntifs-_file_fs_control_information.md)

[**FILE_FS_DEVICE_INFORMATION**](../wdm/ns-wdm-_file_fs_device_information.md)

[**FILE_FS_DRIVER_PATH_INFORMATION**](ns-ntifs-_file_fs_driver_path_information.md)

[**FILE_FS_FULL_SIZE_INFORMATION**](../ntddk/ns-ntddk-_file_fs_full_size_information.md)

[**FILE_FS_OBJECTID_INFORMATION**](../ntddk/ns-ntddk-_file_fs_objectid_information.md)

[**FILE_FS_SIZE_INFORMATION**](../ntddk/ns-ntddk-_file_fs_size_information.md)

[**FILE_FS_VOLUME_INFORMATION**](../ntddk/ns-ntddk-_file_fs_volume_information.md)

[**FltQueryVolumeInformationFile**](../fltkernel/nf-fltkernel-fltqueryvolumeinformationfile.md)

[**IRP_MJ_QUERY_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-query-volume-information)

[**IRP_MJ_SET_VOLUME_INFORMATION**](/windows-hardware/drivers/ifs/irp-mj-set-volume-information)

[Using Nt and Zw Versions of the Native System Services Routines](/windows-hardware/drivers/kernel/using-nt-and-zw-versions-of-the-native-system-services-routines)

[**ZwCreateFile**](../wdm/nf-wdm-zwcreatefile.md)

[**ZwOpenFile**](../wdm/nf-wdm-zwopenfile.md)

[**ZwQueryDirectoryFile**](nf-ntifs-zwquerydirectoryfile.md)

[**ZwQueryInformationFile**](../wdm/nf-wdm-zwqueryinformationfile.md)

[**ZwSetInformationFile**](../wdm/nf-wdm-zwsetinformationfile.md)

[**ZwSetVolumeInformationFile**](nf-ntifs-zwsetvolumeinformationfile.md)
