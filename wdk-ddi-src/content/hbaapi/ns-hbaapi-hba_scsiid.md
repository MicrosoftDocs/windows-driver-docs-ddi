---
UID: NS:hbaapi.HBA_ScsiId
title: HBA_ScsiId
author: windows-driver-content
description: The HBA_ScsiId structure contains information used by the operating system to identify a SCSI logical unit.
old-location: storage\hba_scsiid.htm
tech.root: storage
ms.assetid: c2acb40c-cb6e-45b4-b0be-911f6b37094e
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_SCSIID, HBA_SCSIID, HBA_SCSIID structure [Storage Devices], HBA_ScsiId, HBA_ScsiId structure [Storage Devices], PHBA_SCSIID, PHBA_SCSIID structure pointer [Storage Devices], hbaapi/HBA_ScsiId, hbaapi/PHBA_SCSIID, storage.hba_scsiid, structs-Fibre_855aa506-19ff-469d-8b32-3fc7f9e84ade.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: hbaapi.h
req.include-header: Hbaapi.h
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
-	hbaapi.h
api_name:
-	HBA_SCSIID
product:
- Windows
targetos: Windows
req.typenames: HBA_SCSIID, *PHBA_SCSIID
---

# HBA_ScsiId structure


## -description


The HBA_ScsiId structure contains information used by the operating system to identify a SCSI logical unit.


## -struct-fields




### -field OSDeviceName

Contains a name assigned to the device by the operating system. For example: "\device\ScsiPort3."


### -field ScsiBusNumber

Contains the number assigned by the operating system to SCSI bus that the device is on. 


### -field ScsiTargetNumber

Contains the target ID number assigned by the operating system to the target device.  


### -field ScsiOSLun

Contains the logical unit number assigned by the operating system to the logical unit. 


## -remarks



For a detailed discussion of how the data assigned to members of this structure should be formatted, see the T11 committee's <i>Fibre Channel HBA API</i> specification. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556096">HBA_GetFCPStatistics</a>
 

 

