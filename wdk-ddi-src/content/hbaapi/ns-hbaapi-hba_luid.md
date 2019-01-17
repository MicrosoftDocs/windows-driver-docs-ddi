---
UID: NS:hbaapi.HBA_LUID
title: HBA_LUID
description: The HBA_LUID structure contains the identification descriptor from the device identification page of the vital products data returned by a SCSI INQUIRY command.
old-location: storage\hba_luid.htm
tech.root: storage
ms.assetid: af272e27-6cb4-4f87-9c46-512ac80fa310
ms.date: 03/29/2018
ms.keywords: "*PHBA_LUID, HBA_LUID, HBA_LUID structure [Storage Devices], PHBA_LUID, PHBA_LUID structure pointer [Storage Devices], hbaapi/HBA_LUID, hbaapi/PHBA_LUID, storage.hba_luid, structs-Fibre_32d9473b-e356-41cc-9352-7a142fc3dcc7.xml"
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
-	HBA_LUID
product:
- Windows
targetos: Windows
req.typenames: HBA_LUID, *PHBA_LUID
---

# HBA_LUID structure


## -description


The HBA_LUID structure contains the identification descriptor from the device identification page of the vital products data returned by a SCSI INQUIRY command.


## -struct-fields




### -field buffer

Contains a buffer that holds the identification descriptor.


## -remarks



A vendor specific LUID is not guaranteed to be unique or persistent. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff556060">HBA_FCPBindingEntry2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff556068">HBA_FcpScsiEntryV2</a>
 

 

