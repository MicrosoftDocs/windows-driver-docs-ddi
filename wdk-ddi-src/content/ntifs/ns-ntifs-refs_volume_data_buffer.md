---
UID: NS:ntifs.REFS_VOLUME_DATA_BUFFER
tech.root: ifsk
title: REFS_VOLUME_DATA_BUFFER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the REFS_VOLUME_DATA_BUFFER structure.
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
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: 
req.target-type: 
req.typenames: REFS_VOLUME_DATA_BUFFER, *PREFS_VOLUME_DATA_BUFFER
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
 - REFS_VOLUME_DATA_BUFFER
 - PREFS_VOLUME_DATA_BUFFER
f1_keywords:
 - REFS_VOLUME_DATA_BUFFER
 - ntifs/REFS_VOLUME_DATA_BUFFER
 - PREFS_VOLUME_DATA_BUFFER
 - ntifs/PREFS_VOLUME_DATA_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - REFS_VOLUME_DATA_BUFFER
---

## -description

The **REFS_VOLUME_DATA_BUFFER** structure contains information about an ReFS volume.

## -struct-fields

### -field ByteCount

Size in bytes of this structure.

### -field MajorVersion

Major version number of the ReFS volume.

### -field MinorVersion

Minor version number of the ReFS volume.

### -field BytesPerPhysicalSector

Number of bytes per physical sector on the volume.

### -field VolumeSerialNumber

Unique serial number of the volume.

### -field NumberSectors

Total number of sectors on the volume.

### -field TotalClusters

Total number of clusters on the volume.

### -field FreeClusters

Number of free clusters available on the volume.

### -field TotalReserved

Total number of reserved clusters on the volume.

### -field BytesPerSector

Number of bytes per sector.

### -field BytesPerCluster

Number of bytes per cluster.

### -field MaximumSizeOfResidentFile

Maximum size of a file that can reside entirely within a single cluster.

### -field FastTierDataFillRatio

Fill ratio for the fast tier, expressed as a value between 0 and 10000.

### -field SlowTierDataFillRatio

Fill ratio for the slow tier, expressed as a value between 0 and 10000.

### -field DestagesFastTierToSlowTierRate

Rate at which data is destaged from the fast tier to the slow tier, measured in clusters per second.

### -field MetadataChecksumType

Type of checksum used for metadata.

### -field Reserved0[6]

Reserved0: Reserved for future use.

### -field DriverMajorVersion

Major version number of the file system driver.

### -field DriverMinorVersion

Minor version number of the file system driver.

### -field Reserved[7]

Reserved for future use.

## -remarks

## -see-also

[**FSCTL_GET_REFS_VOLUME_DATA**](ni-ntifs-fsctl_get_refs_volume_data.md)
