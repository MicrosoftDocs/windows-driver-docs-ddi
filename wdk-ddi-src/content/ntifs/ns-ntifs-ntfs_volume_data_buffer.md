---
UID: NS:ntifs.NTFS_VOLUME_DATA_BUFFER
tech.root: ifsk
title: NTFS_VOLUME_DATA_BUFFER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the NTFS_VOLUME_DATA_BUFFER structure.
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
req.typenames: NTFS_VOLUME_DATA_BUFFER, *PNTFS_VOLUME_DATA_BUFFER
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
 - NTFS_VOLUME_DATA_BUFFER
 - PNTFS_VOLUME_DATA_BUFFER
f1_keywords:
 - NTFS_VOLUME_DATA_BUFFER
 - ntifs/NTFS_VOLUME_DATA_BUFFER
 - PNTFS_VOLUME_DATA_BUFFER
 - ntifs/PNTFS_VOLUME_DATA_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - NTFS_VOLUME_DATA_BUFFER
---

## -description

The **NTFS_VOLUME_DATA_BUFFER** structure contains information about an NTFS volume. It's used with the [**FSCTL_GET_NTFS_VOLUME_DATA**](ni-ntifs-fsctl_get_ntfs_volume_data.md) control code.

## -struct-fields

### -field VolumeSerialNumber

The serial number of the volume. This is a unique number assigned to the volume media by the operating system.

### -field NumberSectors

Number of sectors in the specified volume.

### -field TotalClusters

Number of used and free clusters in the specified volume.

### -field FreeClusters

Number of free clusters in the specified volume.

### -field TotalReserved

Number of reserved clusters in the specified volume.

### -field BytesPerSector

Number of bytes in a sector on the specified volume.

### -field BytesPerCluster

Number of bytes in a cluster on the specified volume. This value is also known as the cluster factor.

### -field BytesPerFileRecordSegment

Number of bytes in a file record segment.

### -field ClustersPerFileRecordSegment

Number of clusters in a file record segment.

### -field MftValidDataLength

Length of the master file table (MFT) in bytes.

### -field MftStartLcn

Starting logical cluster number (LCN) of the MFT.

### -field Mft2StartLcn

Starting LCN of the MFT mirror.

### -field MftZoneStart

Starting LCN of the MFT zone.

### -field MftZoneEnd

Ending LCN of the MFT zone.

## -remarks

Reserved clusters are the free clusters reserved for later use by Windows.

The **NTFS_VOLUME_DATA_BUFFER** structure represents the basic information returned by [**FSCTL_GET_NTFS_VOLUME_DATA**](ni-ntifs-fsctl_get_ntfs_volume_data.md). For extended volume information, pass a buffer that is the combined size of the **NTFS_VOLUME_DATA_BUFFER** and [**NTFS_EXTENDED_VOLUME_DATA**](ns-ntifs-ntfs_extended_volume_data.md) structures. Upon success, the buffer returned by **FSCTL_GET_NTFS_VOLUME_DATA** will contain the information associated with both structures. The NTFS_VOLUME_DATA_BUFFER structure will always be filled starting at the beginning of the buffer, with the **NTFS_EXTENDED_VOLUME_DATA** structure immediately following.

## -see-also

[**FSCTL_GET_NTFS_VOLUME_DATA**](ni-ntifs-fsctl_get_ntfs_volume_data.md)

[**NTFS_EXTENDED_VOLUME_DATA**](ns-ntifs-ntfs_extended_volume_data.md)
