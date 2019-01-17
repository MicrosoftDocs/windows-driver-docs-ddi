---
UID: NS:hbaapi.HBA_FcpScsiEntry
title: HBA_FcpScsiEntry
description: The HBA_FcpScsiEntry structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hba_fcpscsientry.htm
tech.root: storage
ms.assetid: 19e40a1b-fcbf-4510-a7c0-aa9a61f2f651
ms.date: 03/29/2018
ms.keywords: "*PHBA_FCPSCSIENTRY, HBA_FCPSCSIENTRY, HBA_FCPSCSIENTRY structure [Storage Devices], HBA_FcpScsiEntry, HBA_FcpScsiEntry structure [Storage Devices], PHBA_FCPSCSIENTRY, PHBA_FCPSCSIENTRY structure pointer [Storage Devices], hbaapi/HBA_FcpScsiEntry, hbaapi/PHBA_FCPSCSIENTRY, storage.hba_fcpscsientry, structs-Fibre_32b32b55-43e6-484c-a7fb-5c477864b735.xml"
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
-	HBA_FCPSCSIENTRY
product:
- Windows
targetos: Windows
req.typenames: HBA_FCPSCSIENTRY, *PHBA_FCPSCSIENTRY
---

# HBA_FcpScsiEntry structure


## -description


The HBA_FcpScsiEntry structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. 


## -struct-fields




### -field ScsiId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a> that holds information that the operating system uses to identify a SCSI device. 


### -field FcpId

Contains a structure of type <a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a> that uniquely identifies the device anywhere on the fibre channel network. 


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556062">HBA_FcpId</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff557191">HBA_ScsiId</a>
 

 

