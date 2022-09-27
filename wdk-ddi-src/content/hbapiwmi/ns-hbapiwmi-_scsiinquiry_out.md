---
UID: NS:hbapiwmi._ScsiInquiry_OUT
title: ScsiInquiry_OUT (hbapiwmi.h)
description: The ScsiInquiry_OUT structure is used to report the output data of the ScsiInquiry WMI method to the WMI client.
old-location: storage\scsiinquiry_out2.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["ScsiInquiry_OUT structure"]
ms.keywords: "*PScsiInquiry_OUT, PScsiInquiry_OUT, PScsiInquiry_OUT structure pointer [Storage Devices], ScsiInquiry_OUT, ScsiInquiry_OUT structure [Storage Devices], _ScsiInquiry_OUT, hbapiwmi/PScsiInquiry_OUT, hbapiwmi/ScsiInquiry_OUT, storage.scsiinquiry_out2, structs-Fibre_2c7df8b3-a571-4e88-b4db-202d2bd39ce8.xml"
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
req.typenames: ScsiInquiry_OUT, *PScsiInquiry_OUT
f1_keywords:
 - _ScsiInquiry_OUT
 - hbapiwmi/_ScsiInquiry_OUT
 - PScsiInquiry_OUT
 - hbapiwmi/PScsiInquiry_OUT
 - ScsiInquiry_OUT
 - hbapiwmi/ScsiInquiry_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hbapiwmi.h
api_name:
 - _ScsiInquiry_OUT
 - PScsiInquiry_OUT
 - ScsiInquiry_OUT
---

# ScsiInquiry_OUT structure (hbapiwmi.h)

## -description

The ScsiInquiry_OUT structure is used to report the output data of the [**ScsiInquiry**](/windows-hardware/drivers/storage/scsiinquiry) WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains a value associated with the WMI class qualifier [**HBA_STATUS**](/windows-hardware/drivers/storage/hba-status) that indicates the result of an HBA query operation.

### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the inquiry command.

### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the inquiry command.

### -field ScsiStatus

Contains the status of the SCSI inquiry command.

### -field ResponseBuffer[1]

Contains the results of the SCSI inquiry command.

## -remarks

The WMI tool suite generates a declaration of the ScsiInquiry_OUT structure in *Hbapiwmi.h* when it compiles the [MSFC_HBAAdapterMethods WMI Class](/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class).

## -see-also

[**HBA_STATUS**](/windows-hardware/drivers/storage/hba-status)

[**ScsiInquiry**](/windows-hardware/drivers/storage/scsiinquiry)
