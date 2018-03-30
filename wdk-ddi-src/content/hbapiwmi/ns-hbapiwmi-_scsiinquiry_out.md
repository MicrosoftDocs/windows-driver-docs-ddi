---
UID: NS:hbapiwmi._ScsiInquiry_OUT
title: "_ScsiInquiry_OUT"
author: windows-driver-content
description: The ScsiInquiry_OUT structure is used to report the output data of the ScsiInquiry WMI method to the WMI client.
old-location: storage\scsiinquiry_out2.htm
old-project: storage
ms.assetid: ea1d6f35-1dc5-4c65-9158-7f85464c5cd7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PScsiInquiry_OUT, PScsiInquiry_OUT, PScsiInquiry_OUT structure pointer [Storage Devices], ScsiInquiry_OUT, ScsiInquiry_OUT structure [Storage Devices], _ScsiInquiry_OUT, hbapiwmi/PScsiInquiry_OUT, hbapiwmi/ScsiInquiry_OUT, storage.scsiinquiry_out2, structs-Fibre_2c7df8b3-a571-4e88-b4db-202d2bd39ce8.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	ScsiInquiry_OUT
product: Windows
targetos: Windows
req.typenames: ScsiInquiry_OUT, *PScsiInquiry_OUT
---

# _ScsiInquiry_OUT structure


## -description


The ScsiInquiry_OUT structure is used to report the output data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation. 


### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the inquiry command. 


### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the inquiry command. 


### -field ScsiStatus

Contains the status of the SCSI inquiry command. 


### -field ResponseBuffer

Contains the results of the SCSI inquiry command. 


#### - SenseBuffer

Contains the SCSI sense data that results from the SCSI inquiry command. 


## -remarks



The WMI tool suite generates a declaration of the ScsiInquiry_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564585">ScsiInquiry</a>
 

 

