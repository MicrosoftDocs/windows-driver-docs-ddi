---
UID: NS:hbapiwmi._ScsiReportLuns_IN
title: _ScsiReportLuns_IN (hbapiwmi.h)
description: The ScsiReportLuns_IN structure is used to deliver input parameter data to the ScsiReportLuns WMI method.
old-location: storage\scsireportluns_in2.htm
tech.root: storage
ms.assetid: 6de38cf4-a543-4cc9-aa6f-1804fc858040
ms.date: 03/29/2018
ms.keywords: "*PScsiReportLuns_IN, PScsiReportLuns_IN, PScsiReportLuns_IN structure pointer [Storage Devices], ScsiReportLuns_IN, ScsiReportLuns_IN structure [Storage Devices], _ScsiReportLuns_IN, hbapiwmi/PScsiReportLuns_IN, hbapiwmi/ScsiReportLuns_IN, storage.scsireportluns_in2, structs-Fibre_29218585-2d91-40f3-bbce-fb23df1e3df9.xml"
ms.topic: struct
f1_keywords:
 - "hbapiwmi/ScsiReportLuns_IN"
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Hbapiwmi.h
api_name:
- ScsiReportLuns_IN
product:
- Windows
targetos: Windows
req.typenames: ScsiReportLuns_IN, *PScsiReportLuns_IN
---

# _ScsiReportLuns_IN structure


## -description


The ScsiReportLuns_IN structure is used to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireportluns6">ScsiReportLuns</a> WMI method. 


## -struct-fields




### -field Cdb

Contains the command descriptor block that holds the SCSI report LUNs command to be sent to the target device. 


### -field HbaPortWWN

Contains a worldwise name for the HBA through which the target is accessed. 


### -field DiscoveredPortWWN

Contains a worldwide name for the port through which the target device is accessed. 


#### - FcLun

Indicates the logical unit number of the logical unit that will receive the SCSI report luns command.


## -remarks



The WMI tool suite generates a declaration of the ScsiReportLuns_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireportluns6">ScsiReportLuns</a>
 

 

