---
UID: NS:hbapiwmi._ScsiReadCapacity_OUT
title: ScsiReadCapacity_OUT (hbapiwmi.h)
description: The ScsiReadCapacity_OUT structure is used to report the output data of the ScsiReadCapacity WMI method to the WMI client.
old-location: storage\scsireadcapacity_out2.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["ScsiReadCapacity_OUT structure"]
ms.keywords: "*PScsiReadCapacity_OUT, PScsiReadCapacity_OUT, PScsiReadCapacity_OUT structure pointer [Storage Devices], ScsiReadCapacity_OUT, ScsiReadCapacity_OUT structure [Storage Devices], _ScsiReadCapacity_OUT, hbapiwmi/PScsiReadCapacity_OUT, hbapiwmi/ScsiReadCapacity_OUT, storage.scsireadcapacity_out2, structs-Fibre_b362afaf-6cf2-4e2b-9239-11d7fdec3d74.xml"
req.header: hbapiwmi.h
req.include-header: Hbapiwmi.h
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
req.typenames: ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT
f1_keywords:
 - _ScsiReadCapacity_OUT
 - hbapiwmi/_ScsiReadCapacity_OUT
 - PScsiReadCapacity_OUT
 - hbapiwmi/PScsiReadCapacity_OUT
 - ScsiReadCapacity_OUT
 - hbapiwmi/ScsiReadCapacity_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hbapiwmi.h
api_name:
 - _ScsiReadCapacity_OUT
 - PScsiReadCapacity_OUT
 - ScsiReadCapacity_OUT
---

# ScsiReadCapacity_OUT structure (hbapiwmi.h)

## -description

The ScsiReadCapacity_OUT structure is used to report the output data of the [**ScsiReadCapacity**](/windows-hardware/drivers/storage/scsireadcapacity6) WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains a value associated with the WMI class qualifier [**HBA_STATUS**](/windows-hardware/drivers/storage/hba-status) that indicates the result of an HBA query operation.

### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the read capacity command.

### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the read capacity command.

### -field ScsiStatus

Contains the status of the SCSI read capacity command.

### -field ResponseBuffer[1]

Contains the results of the SCSI read capacity command.

## -remarks

The WMI tool suite generates a declaration of the ScsiReadCapacity_OUT structure in *Hbapiwmi.h* when it compiles the [MSFC_HBAAdapterMethods WMI Class](/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class).

## -see-also

[**HBA_STATUS**](/windows-hardware/drivers/storage/hba-status)

[**ScsiReadCapacity**](/windows-hardware/drivers/storage/scsireadcapacity6)
