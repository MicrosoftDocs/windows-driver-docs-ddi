---
UID: NS:hbapiwmi._ScsiInquiry_IN
title: _ScsiInquiry_IN (hbapiwmi.h)
description: The ScsiInquiry_IN structure is used by a miniport driver to deliver input parameter data to the ScsiInquiry WMI method.
old-location: storage\scsiinquiry_in2.htm
tech.root: storage
ms.assetid: f7690483-8269-4fb4-9960-9abdbb128b94
ms.date: 03/29/2018
ms.keywords: "*PScsiInquiry_IN, PScsiInquiry_IN, PScsiInquiry_IN structure pointer [Storage Devices], ScsiInquiry_IN, ScsiInquiry_IN structure [Storage Devices], _ScsiInquiry_IN, hbapiwmi/PScsiInquiry_IN, hbapiwmi/ScsiInquiry_IN, storage.scsiinquiry_in2, structs-Fibre_b1f0d146-5bc7-4d98-b97e-ec508b4023c9.xml"
ms.topic: struct
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
- ScsiInquiry_IN
product:
- Windows
targetos: Windows
req.typenames: ScsiInquiry_IN, *PScsiInquiry_IN
---

# _ScsiInquiry_IN structure


## -description


The ScsiInquiry_IN structure is used by a miniport driver to deliver input parameter data to the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> WMI method. 


## -struct-fields




### -field Cdb

Contains the command descriptor block that holds the SCSI inquiry command to be sent to the target device. 


### -field HbaPortWWN

Contains a worldwise name for the HBA through which the target is accessed. 


### -field DiscoveredPortWWN

Contains a worldwide name for the port through which the target device is accessed. 


### -field FcLun

Indicates the logical unit number of the logical unit that will receive the SCSI inquiry command.


## -remarks



The WMI tool suite generates a declaration of the ScsiInquiry_IN structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>
 

 

