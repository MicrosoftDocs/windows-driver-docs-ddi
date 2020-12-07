---
UID: NS:ntdddisk._PARTITION_INFORMATION_GPT
title: _PARTITION_INFORMATION_GPT (ntdddisk.h)
description: PARTITION_INFORMATION_GPT contains information for a GUID Partition Table partition that is not held in common with a Master Boot Record partition.
old-location: storage\partition_information_gpt.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["PARTITION_INFORMATION_GPT structure"]
ms.keywords: "*PPARTITION_INFORMATION_GPT, PARTITION_INFORMATION_GPT, PARTITION_INFORMATION_GPT structure [Storage Devices], PPARTITION_INFORMATION_GPT, PPARTITION_INFORMATION_GPT structure pointer [Storage Devices], SET_PARTITION_INFORMATION_GPT, _PARTITION_INFORMATION_GPT, ntdddisk/PARTITION_INFORMATION_GPT, ntdddisk/PPARTITION_INFORMATION_GPT, storage.partition_information_gpt, structs-disk_dad0a2a5-4351-4940-af39-28f7a4005c14.xml"
req.header: ntdddisk.h
req.include-header: Ntdddisk.h
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
req.typenames: PARTITION_INFORMATION_GPT, *PPARTITION_INFORMATION_GPT
f1_keywords:
 - _PARTITION_INFORMATION_GPT
 - ntdddisk/_PARTITION_INFORMATION_GPT
 - PPARTITION_INFORMATION_GPT
 - ntdddisk/PPARTITION_INFORMATION_GPT
 - PARTITION_INFORMATION_GPT
 - ntdddisk/PARTITION_INFORMATION_GPT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - ntdddisk.h
api_name:
 - PARTITION_INFORMATION_GPT
---

# _PARTITION_INFORMATION_GPT structure


## -description

PARTITION_INFORMATION_GPT contains information for a GUID Partition Table partition that is not held in common with a Master Boot Record partition.

## -struct-fields

### -field PartitionType

Specifies a GUID that uniquely identifies the partition type. The GUID data type is described on the <a href="/windows-hardware/drivers/kernel/using-guids-in-drivers">Using GUIDs in Drivers</a> reference page.

### -field PartitionId

Specifies a GUID that uniquely identifies the partition. The GUID data type is described on the <a href="/windows-hardware/drivers/kernel/using-guids-in-drivers">Using GUIDs in Drivers</a> reference page.

### -field Attributes

Specifies the partition entry attributes used for diagnostics, recovery tools, and other firmware essential to the operation of the device. See Intel's <i>Extensible Firmware Interface</i> specification for further information.

### -field Name

Specifies the partition name in Unicode.

## -see-also

<a href="/windows-hardware/drivers/ddi/ntddk/nf-ntddk-ioreadpartitiontableex">IoReadPartitionTableEx</a>



<a href="/windows-hardware/drivers/ddi/ntdddisk/ns-ntdddisk-_partition_information_ex">PARTITION_INFORMATION_EX</a>
