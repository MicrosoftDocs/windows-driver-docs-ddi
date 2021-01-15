---
UID: NS:ntdddisk._DRIVE_LAYOUT_INFORMATION_GPT
title: _DRIVE_LAYOUT_INFORMATION_GPT (ntdddisk.h)
description: The DRIVE_LAYOUT_INFORMATION_GPT structure reports the drive signature for a GUID Partition Table partition.
old-location: storage\drive_layout_information_gpt.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["DRIVE_LAYOUT_INFORMATION_GPT structure"]
ms.keywords: "*PDRIVE_LAYOUT_INFORMATION_GPT, DRIVE_LAYOUT_INFORMATION_GPT, DRIVE_LAYOUT_INFORMATION_GPT structure [Storage Devices], PDRIVE_LAYOUT_INFORMATION_GPT, PDRIVE_LAYOUT_INFORMATION_GPT structure pointer [Storage Devices], _DRIVE_LAYOUT_INFORMATION_GPT, ntdddisk/DRIVE_LAYOUT_INFORMATION_GPT, ntdddisk/PDRIVE_LAYOUT_INFORMATION_GPT, storage.drive_layout_information_gpt, structs-disk_eca2e047-5de8-4960-9066-28eb0dfedb95.xml"
req.header: ntdddisk.h
req.include-header: Ntddk.h
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
req.typenames: DRIVE_LAYOUT_INFORMATION_GPT, *PDRIVE_LAYOUT_INFORMATION_GPT
f1_keywords:
 - _DRIVE_LAYOUT_INFORMATION_GPT
 - ntdddisk/_DRIVE_LAYOUT_INFORMATION_GPT
 - PDRIVE_LAYOUT_INFORMATION_GPT
 - ntdddisk/PDRIVE_LAYOUT_INFORMATION_GPT
 - DRIVE_LAYOUT_INFORMATION_GPT
 - ntdddisk/DRIVE_LAYOUT_INFORMATION_GPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - _DRIVE_LAYOUT_INFORMATION_GPT
 - PDRIVE_LAYOUT_INFORMATION_GPT
 - DRIVE_LAYOUT_INFORMATION_GPT
---

# _DRIVE_LAYOUT_INFORMATION_GPT structure


## -description

The DRIVE_LAYOUT_INFORMATION_GPT structure reports the drive signature for a GUID Partition Table partition.

## -struct-fields

### -field DiskId

Contains a GUID that uniquely identifies the drive. The GUID data type is described on the <a href="/windows-hardware/drivers/kernel/using-guids-in-drivers">Using GUIDs in Drivers</a> reference page.

### -field StartingUsableOffset

Contains an offset in bytes to the location immediately following the primary partition table. This offset begins the region on the drive where partitions reside, but partition one is not necessarily located precisely at this offset.

### -field UsableLength

Indicates the total usable space in bytes available on the drive.

### -field MaxPartitionCount

Indicates the maximum number of partitions allowed on the drive.

## -remarks

This structure contains the drive layout information that is specific to a drive with a GUID Partition Table partition. It is encapsulated within the <a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information_ex">DRIVE_LAYOUT_INFORMATION_EX</a> structure. For further information see Intel's <i>Extensible Firmware Interface</i> specification.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_drive_layout_information_ex">DRIVE_LAYOUT_INFORMATION_EX</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreadpartitiontable">IoReadPartitionTable</a>



<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-iowritepartitiontable">IoWritePartitionTable</a>

