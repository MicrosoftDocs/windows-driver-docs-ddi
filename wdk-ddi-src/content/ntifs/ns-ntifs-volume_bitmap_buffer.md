---
UID: NS:ntifs.VOLUME_BITMAP_BUFFER
tech.root: ifsk
title: VOLUME_BITMAP_BUFFER
ms.date: 02/14/2025
targetos: Windows
description: Learn more about the VOLUME_BITMAP_BUFFER structure.
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
req.typenames: VOLUME_BITMAP_BUFFER, *PVOLUME_BITMAP_BUFFER
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
 - VOLUME_BITMAP_BUFFER
 - PVOLUME_BITMAP_BUFFER
f1_keywords:
 - VOLUME_BITMAP_BUFFER
 - ntifs/VOLUME_BITMAP_BUFFER
 - PVOLUME_BITMAP_BUFFER
 - ntifs/PVOLUME_BITMAP_BUFFER
dev_langs:
 - c++
helpviewer_keywords:
 - VOLUME_BITMAP_BUFFER
---

## -description

The **VOLUME_BITMAP_BUFFER** structure contains a bitmap of occupied and available clusters on a disk. This structure is the output buffer for the [**FSCTL_GET_VOLUME_BITMAP**](ni-ntifs-fsctl_get_volume_bitmap.md) control code.

## -struct-fields

### -field StartingLcn

Starting logical cluster number (LCN) requested as an input to the operation.

### -field BitmapSize

Number of clusters on the volume, starting from the starting LCN returned in **StartingLcn**.

### -field Buffer[1]

Array of bytes containing the bitmap that the operation returns. The bitmap is bitwise from bit zero of the bitmap to the end. Thus, starting at the requested cluster, the bitmap goes from bit 0 of byte 0, bit 1 of byte 0 ... bit 7 of byte 0, bit 0 of byte 1, and so on. The value 1 indicates that the cluster is allocated (in use). The value 0 indicates that the cluster is not allocated (free).

## -remarks

**BitmapSize** is the number of clusters on the volume starting from **StartingLcn**. For example, suppose there are 0xD3F7 clusters on the volume. If you start the bitmap query at LCN 0xA007, then both the FAT and NTFS file systems will round down the returned starting LCN to LCN 0xA000. The value returned in the **BitmapSize** member will be (0xD3F7 – 0xA000), or 0x33F7.

## -see-also

[**FSCTL_GET_VOLUME_BITMAP**](ni-ntifs-fsctl_get_volume_bitmap.md)
