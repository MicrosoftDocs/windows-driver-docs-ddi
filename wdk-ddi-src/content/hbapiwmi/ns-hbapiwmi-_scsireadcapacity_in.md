---
UID: NS:hbapiwmi._ScsiReadCapacity_IN
title: _ScsiReadCapacity_IN (hbapiwmi.h)
description: The ScsiReadCapacity_IN structure is used to deliver input parameter data to the ScsiReadCapacity WMI method.
old-location: storage\scsireadcapacity_in2.htm
tech.root: storage
ms.assetid: 6d5aa608-9ee7-45a6-bd2f-13a5b8338437
ms.date: 03/29/2018
keywords: ["_ScsiReadCapacity_IN structure"]
ms.keywords: "*PScsiReadCapacity_IN, PScsiReadCapacity_IN, PScsiReadCapacity_IN structure pointer [Storage Devices], ScsiReadCapacity_IN, ScsiReadCapacity_IN structure [Storage Devices], _ScsiReadCapacity_IN, hbapiwmi/PScsiReadCapacity_IN, hbapiwmi/ScsiReadCapacity_IN, storage.scsireadcapacity_in2, structs-Fibre_235165a1-b938-461a-9e4d-f555eae34119.xml"
f1_keywords:
 - "hbapiwmi/ScsiReadCapacity_IN"
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
- ScsiReadCapacity_IN
product:
- Windows
targetos: Windows
req.typenames: ScsiReadCapacity_IN, *PScsiReadCapacity_IN
---

# _ScsiReadCapacity_IN structure


## -description


The ScsiReadCapacity_IN structure is used to deliver input parameter data to the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireadcapacity6">ScsiReadCapacity</a> WMI method. 


## -struct-fields




### -field Cdb

Contains the command descriptor block that holds the SCSI read capacity command to be sent to the target device. 


### -field HbaPortWWN

Contains a worldwise name for the HBA through which the target is accessed. 


### -field DiscoveredPortWWN

Contains a worldwide name for the port through which the target device is accessed. 


### -field FcLun

Indicates the logical unit number of the logical unit that will receive the SCSI read capacity command.


## -remarks



The WMI tool suite generates a declaration of the ScsiReadCapacity_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://docs.microsoft.com/windows-hardware/drivers/storage/msfc-hbaadaptermethods-wmi-class">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/storage/scsireadcapacity6">ScsiReadCapacity</a>
 

 

