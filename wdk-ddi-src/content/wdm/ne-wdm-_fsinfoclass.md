---
UID: NE:wdm._FSINFOCLASS
title: _FSINFOCLASS (wdm.h)
description: The FS_INFORMATION_CLASS enumeration contains the information class constants that specify what type of information structure is present for a set or a query operation.
old-location: ifsk\fs_information_class.htm
tech.root: ifsk
ms.assetid: 8A8F938D-8F6B-47E0-963F-8E8B14033802
ms.date: 04/16/2018
keywords: ["_FSINFOCLASS enumeration"]
ms.keywords: "*PFS_INFORMATION_CLASS, FS_INFORMATION_CLASS, FS_INFORMATION_CLASS enumeration [Installable File System Drivers], FileFsAttributeInformation, FileFsControlInformation, FileFsDeviceInformation, FileFsDriverPathInformation, FileFsFullSizeInformation, FileFsLabelInformation, FileFsObjectIdInformation, FileFsSectorSizeInformation, FileFsSizeInformation, FileFsVolumeFlagsInformation, FileFsVolumeInformation, _FSINFOCLASS, ifsk.fs_information_class, wdm/FS_INFORMATION_CLASS, wdm/FileFsAttributeInformation, wdm/FileFsControlInformation, wdm/FileFsDeviceInformation, wdm/FileFsDriverPathInformation, wdm/FileFsFullSizeInformation, wdm/FileFsLabelInformation, wdm/FileFsObjectIdInformation, wdm/FileFsSectorSizeInformation, wdm/FileFsSizeInformation, wdm/FileFsVolumeFlagsInformation, wdm/FileFsVolumeInformation"
f1_keywords:
 - "wdm/FS_INFORMATION_CLASS"
 - "FS_INFORMATION_CLASS"
req.header: wdm.h
req.include-header: 
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
- wdm.h
api_name:
- FS_INFORMATION_CLASS
targetos: Windows
req.typenames: FS_INFORMATION_CLASS, *PFS_INFORMATION_CLASS
---

# _FSINFOCLASS enumeration


## -description



   The FS_INFORMATION_CLASS enumeration contains the information class constants that specify what type of information structure is present for a set or a query operation.
  


## -enum-fields




### -field FileFsVolumeInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_volume_information">FILE_FS_VOLUME_INFORMATION</a> structure that contains information about the volume such as the volume label, serial number, and creation time. 


### -field FileFsLabelInformation

Use a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_label_information">FILE_FS_LABEL_INFORMATION</a> structure to set information a volume label. 


### -field FileFsSizeInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_size_information">FILE_FS_SIZE_INFORMATION</a> structure containing information about the amount of space on the volume that is available to the user that is associated with the calling thread. 


### -field FileFsDeviceInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/wdm/ns-wdm-_file_fs_device_information">FILE_FS_DEVICE_INFORMATION</a> structure that contains device information for the volume. 


### -field FileFsAttributeInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_attribute_information">FILE_FS_ATTRIBUTE_INFORMATION</a> structure that contains attribute information about the file system responsible for the volume. 


### -field FileFsControlInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_control_information">FILE_FS_CONTROL_INFORMATION</a> structure that contains file system control information about the volume. 


### -field FileFsFullSizeInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_full_size_information">FILE_FS_FULL_SIZE_INFORMATION</a> structure that contains information about the total amount of space available on the volume. 


### -field FileFsObjectIdInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_objectid_information">FILE_FS_OBJECTID_INFORMATION</a> structure that contains file-system-specific object ID information for the volume. Note that this is not the same as the (GUID-based) unique volume name that is assigned by the operating system. 


### -field FileFsDriverPathInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntifs/ns-ntifs-_file_fs_driver_path_information">FILE_FS_DRIVER_PATH_INFORMATION</a> structure that contains information about whether a specified driver is in the I/O path for the volume. The originator of the IRP_MJ_QUERY_VOLUME_INFORMATION request must store the name of the driver into the FILE_FS_DRIVER_PATH_INFORMATION structure before sending the IRP to the file system volume device stack. 


### -field FileFsVolumeFlagsInformation

Use a <b>FILE_FS_VOLUME_FLAGS_INFORMATION</b> structure to set the flags for a volume. 


### -field FileFsSectorSizeInformation

Return a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/ntddk/ns-ntddk-_file_fs_sector_size_information">FILE_FS_SECTOR_SIZE_INFORMATION</a> structure that contains information about the physical and logical sector sizes of a volume.

### -field FileFsDataCopyInformation
Returns a [**FILE_FS_DATA_COPY_INFORMATION**] structure that contains the number of data copies.

### -field FileFsMetadataSizeInformation
Returns a [**FILE_FS_METADATA_SIZE_INFORMATION**] structure that contains the metadata size information.

### -field FileFsFullSizeInformationEx 
Returns a [**FILE_FS_FULL_SIZE_INFORMATION_EX**](../ntddk/ns-ntddk-_file_fs_full_size_information_ex.md) structure that contains information about the total amount of space available on the volume. 


### -field FileFsMaximumInformation

End of this enumeration.

