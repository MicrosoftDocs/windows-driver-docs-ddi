---
UID: NS:hbapiwmi._ScsiReportLuns_OUT
title: "_ScsiReportLuns_OUT"
author: windows-driver-content
description: The ScsiReportLuns_OUT structure is used to report the output parameter data of the ScsiReportLuns WMI method to the WMI client.
old-location: storage\scsireportluns_out2.htm
old-project: storage
ms.assetid: 93663b88-e750-4280-b5c1-798cc0f848b7
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PScsiReportLuns_OUT, PScsiReportLuns_OUT, PScsiReportLuns_OUT structure pointer [Storage Devices], ScsiReportLuns_OUT, ScsiReportLuns_OUT structure [Storage Devices], _ScsiReportLuns_OUT, hbapiwmi/PScsiReportLuns_OUT, hbapiwmi/ScsiReportLuns_OUT, storage.scsireportluns_out2, structs-Fibre_3c117d4b-f151-45af-84bb-ef6f800967aa.xml"
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
-	ScsiReportLuns_OUT
product:
- Windows
targetos: Windows
req.typenames: ScsiReportLuns_OUT, *PScsiReportLuns_OUT
---

# _ScsiReportLuns_OUT structure


## -description


The ScsiReportLuns_OUT structure is used to report the output parameter data of the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a> WMI method to the WMI client.


## -struct-fields




### -field HBAStatus

Contains a value associated with the WMI class qualifier <a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a> that indicates the result of an HBA query operation. 


### -field ResponseBufferSize

Indicates the size in bytes of the buffer that will hold the results of the inquiry command. 


### -field SenseBufferSize

Indicates the size in bytes of the buffer that will hold the SCSI sense data that results from the inquiry command. 


### -field ScsiStatus

Contains the status of the SCSI report LUNs command. 


### -field ResponseBuffer

Contains the results of the SCSI report LUNs command. 


#### - SenseBuffer

Contains the SCSI sense data that results from the SCSI report LUNs command. 


## -remarks



The WMI tool suite generates a declaration of the ScsiReportLuns_OUT structure in <i>Hbapiwmi.h </i>when it compiles the <a href="https://msdn.microsoft.com/library/windows/hardware/ff562506">MSFC_HBAAdapterMethods WMI Class</a>.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff557233">HBA_STATUS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564918">ScsiReportLuns</a>
 

 

