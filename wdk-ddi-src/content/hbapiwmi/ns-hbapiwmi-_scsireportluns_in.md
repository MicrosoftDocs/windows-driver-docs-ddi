---
UID: NS:hbapiwmi._ScsiReportLuns_IN
title: ScsiReportLuns_IN (hbapiwmi.h)
description: The ScsiReportLuns_IN structure is used to deliver input parameter data to the ScsiReportLuns WMI method.
old-location: storage\scsireportluns_in2.htm
tech.root: storage
ms.date: 08/26/2022
keywords: ["ScsiReportLuns_IN structure"]
ms.keywords: "*PScsiReportLuns_IN, PScsiReportLuns_IN, PScsiReportLuns_IN structure pointer [Storage Devices], ScsiReportLuns_IN, ScsiReportLuns_IN structure [Storage Devices], _ScsiReportLuns_IN, hbapiwmi/PScsiReportLuns_IN, hbapiwmi/ScsiReportLuns_IN, storage.scsireportluns_in2, structs-Fibre_29218585-2d91-40f3-bbce-fb23df1e3df9.xml"
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
req.typenames: ScsiReportLuns_IN, *PScsiReportLuns_IN
f1_keywords:
 - _ScsiReportLuns_IN
 - hbapiwmi/_ScsiReportLuns_IN
 - PScsiReportLuns_IN
 - hbapiwmi/PScsiReportLuns_IN
 - ScsiReportLuns_IN
 - hbapiwmi/ScsiReportLuns_IN
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Hbapiwmi.h
api_name:
 - _ScsiReportLuns_IN
 - PScsiReportLuns_IN
 - ScsiReportLuns_IN
---

# ScsiReportLuns_IN structure (hbapiwmi.h)

## -description

The ScsiReportLuns_IN structure is used to deliver input parameter data to the [**ScsiReportLuns**](/windows-hardware/drivers/storage/scsireportluns6) WMI method.

## -struct-fields

### -field Cdb[12]

Contains the command descriptor block that holds the SCSI report LUNs command to be sent to the target device.

### -field HbaPortWWN[8]

Contains a worldwise name for the HBA through which the target is accessed.

### -field DiscoveredPortWWN[8]

Contains a worldwide name for the port through which the target device is accessed.

## -remarks

The WMI tool suite generates a declaration of the ScsiReportLuns_IN structure in *Hbapiwmi.h* when it compiles the [MSFC_HBAAdapterMethods WMI Class](/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class).

## -see-also

[**ScsiReportLuns**](/windows-hardware/drivers/storage/scsireportluns6)
