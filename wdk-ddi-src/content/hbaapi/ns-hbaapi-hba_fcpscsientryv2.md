---
UID: NS:hbaapi.HBA_FcpScsiEntryV2
title: HBA_FcpScsiEntryV2
author: windows-driver-content
description: The HBA_FcpScsiEntryV2 structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit.
old-location: storage\hba_fcpscsientryv2.htm
old-project: storage
ms.assetid: 28f0118b-8c16-4075-8dc9-78e1e2636f02
ms.author: windowsdriverdev
ms.date: 2/24/2018
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
product: Windows
targetos: Windows
req.typenames: HBA_FCPSCSIENTRYV2, *PHBA_FCPSCSIENTRYV2
---

# HBA_FcpScsiEntryV2 structure


## -description


The HBA_FcpScsiEntryV2 structure defines a mapping between an operating system identifier for a logical unit and the corresponding fibre channel protocol (FCP) identifier for the logical unit. 


## -syntax


````
typedef struct HBA_FcpScsiEntryV2 {
  HBA_SCSIID ScsiId;
  HBA_FCPID  FcpId;
  HBA_LUID   LUID;
} HBA_FCPSCSIENTRYV2, *PHBA_FCPSCSIENTRYV2;
````


## -struct-fields




### -field ScsiId

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a> that holds information that the operating system uses to identify a SCSI device. 


### -field FcpId

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a> that uniquely identifies the device anywhere on the fibre channel network. 


### -field LUID

Contains a structure of type <a href="..\hbaapi\ns-hbaapi-hba_luid.md">HBA_LUID</a> that holds a logical unit descriptor for the device that the operating system derives from SCSI inquiry data. 


## -remarks



The HBA_FcpScsiEntryV2 structure includes all of the information contained in the <a href="..\hbaapi\ns-hbaapi-hba_fcpscsientry.md">HBA_FcpScsiEntry</a> structure and, in addition, contains the identification descriptor for the logical unit derived from SCSI inquiry data.




## -see-also

<a href="..\hbaapi\ns-hbaapi-hba_fcpid.md">HBA_FcpId</a>



<a href="..\hbaapi\ns-hbaapi-hba_scsiid.md">HBA_ScsiId</a>



<a href="..\hbaapi\ns-hbaapi-hba_fcpscsientry.md">HBA_FcpScsiEntry</a>



<a href="..\hbaapi\ns-hbaapi-hba_luid.md">HBA_LUID</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_FcpScsiEntryV2 structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

