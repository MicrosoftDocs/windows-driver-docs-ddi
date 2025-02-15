---
UID: NS:ntifs.NTFS_EXTENDED_VOLUME_DATA
tech.root: ifsk
title: NTFS_EXTENDED_VOLUME_DATA
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the NTFS_EXTENDED_VOLUME_DATA structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: ntifs.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows XP
req.target-min-winversvr: 
req.target-type: 
req.typenames: NTFS_EXTENDED_VOLUME_DATA, *PNTFS_EXTENDED_VOLUME_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntifs.h
api_name:
 - NTFS_EXTENDED_VOLUME_DATA
 - PNTFS_EXTENDED_VOLUME_DATA
f1_keywords:
 - NTFS_EXTENDED_VOLUME_DATA
 - ntifs/NTFS_EXTENDED_VOLUME_DATA
 - PNTFS_EXTENDED_VOLUME_DATA
 - ntifs/PNTFS_EXTENDED_VOLUME_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - NTFS_EXTENDED_VOLUME_DATA
---

## -description

The **NTFS_EXTENDED_VOLUME_DATA** structure contains extended information about an NTFS volume. It's used with the [**FSCTL_GET_NTFS_VOLUME_DATA**](ni-ntifs-fsctl_get_ntfs_volume_data.md) control code.

## -struct-fields

### -field ByteCount

Total bytes of the structure.

### -field MajorVersion

Major version for an NTFS volume.

### -field MinorVersion

Minor version for an NTFS volume.

### -field BytesPerPhysicalSector

Number of bytes per physical sector on the device.

### -field LfsMajorVersion

Major version of the Log File Service (LFS) used by NTFS.

### -field LfsMinorVersion

Minor version of the LFS used by NTFS.

### -field MaxDeviceTrimExtentCount

Maximum number of trim extents that the device can handle in a single trim operation.

### -field MaxDeviceTrimByteCount

Maximum number of bytes that can be trimmed in a single device trim operation.

### -field MaxVolumeTrimExtentCount

Maximum number of trim extents that the volume can handle in a single trim operation.

### -field MaxVolumeTrimByteCount

Maximum number of bytes that can be trimmed in a single volume trim operation.

## -see-also

[**FSCTL_GET_NTFS_VOLUME_DATA**](ni-ntifs-fsctl_get_ntfs_volume_data.md)

[**NTFS_VOLUME_DATA_BUFFER**](ns-ntifs-ntfs_volume_data_buffer.md)
