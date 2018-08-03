---
UID: NS:hbaapi.HBA_FcpScsiEntryV2
title: HBA_FcpScsiEntryV2
author: windows-driver-content
description: The HBA_FcpScsiEntryV2 structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hba_fcpscsientryv2.htm
tech.root: storage
ms.assetid: 28f0118b-8c16-4075-8dc9-78e1e2636f02
ms.author: windowsdriverdev
ms.date: 3/29/2018
ms.keywords: "*PHBA_FCPSCSIENTRYV2, HBA_FCPSCSIENTRYV2, HBA_FCPSCSIENTRYV2 structure [Storage Devices], HBA_FcpScsiEntryV2, HBA_FcpScsiEntryV2 structure [Storage Devices], PHBA_FCPSCSIENTRYV2, PHBA_FCPSCSIENTRYV2 structure pointer [Storage Devices], hbaapi/HBA_FcpScsiEntryV2, hbaapi/PHBA_FCPSCSIENTRYV2, storage.hba_fcpscsientryv2, structs-Fibre_b450dd9b-aeb7-4ba1-86df-4bdc6ef34e5a.xml"
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
-	HBA_FCPSCSIENTRYV2
product:
- Windows
targetos: Windows
req.typenames: HBA_FCPSCSIENTRYV2, *PHBA_FCPSCSIENTRYV2
---

# HBA_FcpScsiEntryV2 structure


## -description


The HBA_FcpScsiEntryV2 structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. 


## -struct-fields




### -field ScsiId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a> that holds information that the operating system uses to identify a SCSI device. 


### -field FcpId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> that uniquely identifies the device anywhere on the fibre channel network. 


### -field LUID

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557091">HBA_LUID</a> that holds a logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


## -remarks



The HBA_FcpScsiEntryV2 structure includes all of the information contained in the <a href="https://msdn.microsoft.com/library/windows/hardware/ff556064">HBA_FcpScsiEntry</a> structure and, in addition, contains the identification descriptor for the logical unit derived from SCSI inquiry data.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556064">HBA_FcpScsiEntry</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557091">HBA_LUID</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a>
 

 

