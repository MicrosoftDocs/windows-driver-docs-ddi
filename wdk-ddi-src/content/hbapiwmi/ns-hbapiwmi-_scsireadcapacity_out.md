---
UID: NS:hbapiwmi._ScsiReadCapacity_OUT
title: "_ScsiReadCapacity_OUT" (hbapiwmi.h)
description: The ScsiReadCapacity_OUT structure is used to report the output data of the ScsiReadCapacity WMI method to the WMI client.
old-location: storage\scsireadcapacity_out2.htm
tech.root: storage
ms.assetid: bf295061-42d6-4f2e-a39e-9bac440b0d93
ms.date: 03/29/2018
ms.keywords: "*PScsiReadCapacity_OUT, PScsiReadCapacity_OUT, PScsiReadCapacity_OUT structure pointer [Storage Devices], ScsiReadCapacity_OUT, ScsiReadCapacity_OUT structure [Storage Devices], _ScsiReadCapacity_OUT, hbapiwmi/PScsiReadCapacity_OUT, hbapiwmi/ScsiReadCapacity_OUT, storage.scsireadcapacity_out2, structs-Fibre_b362afaf-6cf2-4e2b-9239-11d7fdec3d74.xml"
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Hbapiwmi.h
api_name:
-	ScsiReadCapacity_OUT
product:
- Windows
targetos: Windows
req.typenames: ScsiReadCapacity_OUT, *PScsiReadCapacity_OUT
---

# _ScsiReadCapacity_OUT structure


## -description


The ScsiReadCapacity_OUT structure is used to report the output data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation. 


### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the read capacity command. 


### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the read capacity command. 


### -field ScsiStatus

Contains the status of the SCSI read capacity command. 


### -field ResponseBuffer

Contains the results of the SCSI read capacity command. 


#### - SenseBuffer

Contains the SCSI sense data that results from the SCSI read capacity command. 


## -remarks



The WMI tool suite generates a declaration of the ScsiReadCapacity_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564890">ScsiReadCapacity</a>
 

 

