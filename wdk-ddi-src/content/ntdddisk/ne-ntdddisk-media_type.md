---
UID: NE:ntdddisk._MEDIA_TYPE
tech.root: storage
title: MEDIA_TYPE
ms.date: 09/30/2022
targetos: Windows
description: Learn more about the MEDIA_TYPE enumeration.
prerelease: false
req.construct-type: enumeration
req.ddi-compliance: 
req.header: ntdddisk.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _MEDIA_TYPE
 - PMEDIA_TYPE
 - MEDIA_TYPE
f1_keywords:
 - _MEDIA_TYPE
 - ntdddisk/_MEDIA_TYPE
 - PMEDIA_TYPE
 - ntdddisk/PMEDIA_TYPE
 - MEDIA_TYPE
 - ntdddisk/MEDIA_TYPE
dev_langs:
 - c++
helpviewer_keywords:
 - _MEDIA_TYPE
---

## -description

The MEDIA\_TYPE enumerators are used in conjunction with the [**IOCTL\_DISK\_FORMAT\_TRACKS**](ni-ntdddisk-ioctl_disk_format_tracks.md) request to format the specified set of contiguous tracks on the disk.

## -enum-fields

### -field Unknown

Format is unknown.

### -field F5_1Pt2_512

Indicates 5.25", 1.2 MB, 512 bytes/sector media.

### -field F3_1Pt44_512

Indicates 3.5", 1.44 MB, 512 bytes/sector media.

### -field F3_2Pt88_512

Indicates 3.5", 2.88 MB, 512 bytes/sector media.

### -field F3_20Pt8_512

Indicates 3.5", 20.8 MB, 512 bytes/sector media.

### -field F3_720_512

Indicates 3.5", 720 KB, 512 bytes/sector media.

### -field F5_360_512

Indicates 5.25", 360 KB, 512 bytes/sector media.

### -field F5_320_512

Indicates 5.25", 320 KB, 512 bytes/sector media.

### -field F5_320_1024

Indicates 5.25", 320 KB, 1024 bytes/sector media.

### -field F5_180_512

Indicates 5.25", 180 KB, 512 bytes/sector media.

### -field F5_160_512

Indicates 5.25", 160 KB, 512 bytes/sector media.

### -field RemovableMedia

Indicates removable media other than a floppy disk.

### -field FixedMedia

Indicates fixed hard disk media.

### -field F3_120M_512

Indicates 3.5", 120 MB media.

### -field F3_640_512

Indicates 3.5", 640 KB, 512 bytes/sector media.

### -field F5_640_512

Indicates 5.25", 640 KB, 512 bytes/sector media.

### -field F5_720_512

Indicates 5.25", 720 KB, 512 bytes/sector media.

### -field F3_1Pt2_512

Indicates 3.5", 1.2 MB, 512 bytes/sector media.

### -field F3_1Pt23_1024

Indicates 3.5", 1.23 MB, 1024 bytes/sector media.

### -field F5_1Pt23_1024

Indicates 5.25", 1.23 MB, 1024 bytes/sector media.

### -field F3_128Mb_512

Indicates 3.5" magneto-optical (MO), 128 MB, 512 bytes/sector media.

### -field F3_230Mb_512

Indicates 3.5" magneto-optical (MO), 230 MB, 512 bytes/sector media.

### -field F8_256_128

Indicates 8", 256 KB, 128 bytes/sector media.

### -field F3_200Mb_512

3.5", 200M Floppy (HiFD)

### -field F3_240M_512

3.5", 240Mb Floppy (HiFD)

### -field F3_32M_512

3.5", 32Mb Floppy

## -remarks

The caller of the IOCTL\_DISK\_FORMAT\_TRACK request indicates the disk size and number of bytes per sector, along with other formatting information, by specifying one of these values in the **MediaType** member of the [**FORMAT\_PARAMETERS**](ns-ntdddisk-_format_parameters.md) structure.

Removable disks include zip drivers, jaz drives, magneto-optical (MO) drives, and LS-120 floppies as well as regular floppies.

## -see-also

[**IOCTL\_DISK\_FORMAT\_TRACKS**](ni-ntdddisk-ioctl_disk_format_tracks.md)

[**FORMAT\_PARAMETERS**](ns-ntdddisk-_format_parameters.md)
