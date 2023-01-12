---
UID: NS:hbapiwmi._ScsiReportLuns_OUT
title: ScsiReportLuns_OUT (hbapiwmi.h)
description: The ScsiReportLuns_OUT structure is used to report the output parameter data of the ScsiReportLuns WMI method to the WMI client.
old-location: storage\scsireportluns_out2.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["ScsiReportLuns_OUT structure"]
ms.keywords: "*PScsiReportLuns_OUT, PScsiReportLuns_OUT, PScsiReportLuns_OUT structure pointer [Storage Devices], ScsiReportLuns_OUT, ScsiReportLuns_OUT structure [Storage Devices], _ScsiReportLuns_OUT, hbapiwmi/PScsiReportLuns_OUT, hbapiwmi/ScsiReportLuns_OUT, storage.scsireportluns_out2, structs-Fibre_3c117d4b-f151-45af-84bb-ef6f800967aa.xml"
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
req.typenames: ScsiReportLuns_OUT, *PScsiReportLuns_OUT
f1_keywords:
 - _ScsiReportLuns_OUT
 - hbapiwmi/_ScsiReportLuns_OUT
 - PScsiReportLuns_OUT
 - hbapiwmi/PScsiReportLuns_OUT
 - ScsiReportLuns_OUT
 - hbapiwmi/ScsiReportLuns_OUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hbapiwmi.h
api_name:
 - _ScsiReportLuns_OUT
 - PScsiReportLuns_OUT
 - ScsiReportLuns_OUT
---

# ScsiReportLuns_OUT structure (hbapiwmi.h)

## -description

The ScsiReportLuns_OUT structure is used to report the output parameter data of the [**ScsiReportLuns**](/windows-hardware/drivers/storage/scsireportluns6) WMI method to the WMI client.

## -struct-fields

### -field HBAStatus

Contains a value associated with the WMI class qualifier [**HBA_STATUS**](/windows-hardware/drivers/storage/hba-status) that indicates the result of an HBA query operation.

### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the inquiry command.

### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the inquiry command.

### -field ScsiStatus

Contains the status of the SCSI report LUNs command.

### -field ResponseBuffer[1]

Contains the results of the SCSI report LUNs command.

## -remarks

The WMI tool suite generates a declaration of the ScsiReportLuns_OUT structure in *Hbapiwmi.h* when it compiles the [MSFC_HBAAdapterMethods WMI Class](/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class).

## -see-also

[**HBA_STATUS**](/windows-hardware/drivers/storage/hba-status)

[**ScsiReportLuns**](/windows-hardware/drivers/storage/scsireportluns6)
