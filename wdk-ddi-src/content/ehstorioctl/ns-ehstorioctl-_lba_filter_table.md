---
UID: NS:ehstorioctl._LBA_FILTER_TABLE
title: LBA_FILTER_TABLE (ehstorioctl.h)
description: The LBA_FILTER_TABLE structure contains the LBA ranges whose access is controlled by a silo driver.
old-location: storage\lba_filter_table.htm
tech.root: storage
ms.date: 05/20/2022
keywords: ["LBA_FILTER_TABLE structure"]
ms.keywords: "*PLBA_FILTER_TABLE, LBA_FILTER_TABLE, LBA_FILTER_TABLE structure [Storage Devices], PLBA_FILTER_TABLE, PLBA_FILTER_TABLE structure pointer [Storage Devices], _LBA_FILTER_TABLE, ehstorioctl/LBA_FILTER_TABLE, ehstorioctl/PLBA_FILTER_TABLE, storage.lba_filter_table"
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
req.target-type: Windows
req.target-min-winverclnt: Available starting with Windows 8
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
req.typenames: LBA_FILTER_TABLE, *PLBA_FILTER_TABLE
f1_keywords:
 - _LBA_FILTER_TABLE
 - ehstorioctl/_LBA_FILTER_TABLE
 - PLBA_FILTER_TABLE
 - ehstorioctl/PLBA_FILTER_TABLE
 - LBA_FILTER_TABLE
 - ehstorioctl/LBA_FILTER_TABLE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - _LBA_FILTER_TABLE
 - PLBA_FILTER_TABLE
 - LBA_FILTER_TABLE
---

# LBA_FILTER_TABLE structure

## -description

The **LBA_FILTER_TABLE** structure contains the LBA ranges whose access is controlled by a silo driver. The LBA filter entries in the table define bands on a storage device that are managed by a silo driver.  A silo drivers send the LBA filter table to the enhanced storage class driver in an [**IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE**](ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md) request.

## -struct-fields

### -field StructSize

The size of this structure. This is set to ```sizeof(LBA_FILTER_TABLE)```.

### -field GlobalReadLock

If TRUE, LBAs not included in the filter table are not readable. Otherwise unfiltered LBAs are readable if FALSE.

### -field Reserved1

Reserved.

### -field GlobalWriteLock

If TRUE, LBAs not included in the filter table are not writeable. Otherwise unfiltered LBAs are writeable if FALSE.

### -field Reserved2

Reserved.

### -field LbaFilterCount

The number of filter entries in the filter table.

### -field LbaFilterSize

The size in bytes of a filter table entry. This must be set to **sizeof**(LBA_FILTER_TABLE_ENTRY).

### -field LbaFilterOffset

The offset of the LBA filter table from the beginning of this structure. This will typically be ```sizeof(LBA_FILTER_TABLE)```.

## -remarks

LBA ranges not included in any filter table entries are considered part of the global band for the device. These ranges are managed independently by the Enhanced Storage Class driver. Access for these ranges is determined by the settings in **GlobalReadLock** and **GlobalWriteLock**.

Following the **LBA_FILTER_TABLE** structure is an array of 0 or more [**LBA_FILTER_TABLE_ENTRY**](ns-ehstorioctl-_lba_filter_table_entry.md) structures. Each **LBA_FILTER_TABLE_ENTRY** defines an individual band whose access is controlled by the silo driver through the direction of band management requests forwarded by the Enhanced Storage Class driver. **LBA_FILTER_TABLE_ENTRY** structures can occur in any order, however, an LBA range in  a table entry must not overlap with an LBA range from another table entry.

## -see-also

[**IOCTL_EHSTOR_DRIVER_UPDATE_LBA_FILTER_TABLE**](ni-ehstorioctl-ioctl_ehstor_driver_update_lba_filter_table.md)

[**LBA_FILTER_TABLE_ENTRY**](ns-ehstorioctl-_lba_filter_table_entry.md)
