---
UID: NS:hbaapi.HBA_ScsiId
title: HBA_ScsiId
author: windows-driver-content
description: The HBA_ScsiId structure contains information used by the operating system to identify a SCSI logical unit.
old-location: storage\hba_scsiid.htm
old-project: storage
ms.assetid: c2acb40c-cb6e-45b4-b0be-911f6b37094e
ms.author: windowsdriverdev
ms.date: 1/10/2018
ms.keywords: HBA_ScsiId structure [Storage Devices], structs-Fibre_855aa506-19ff-469d-8b32-3fc7f9e84ade.xml, storage.hba_scsiid, HBA_SCSIID structure [Storage Devices], *PHBA_SCSIID, hbaapi/HBA_ScsiId, hbaapi/PHBA_SCSIID, PHBA_SCSIID structure pointer [Storage Devices], HBA_SCSIID, PHBA_SCSIID, HBA_ScsiId
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	hbaapi.h
apiname:
-	HBA_SCSIID
product: Windows
targetos: Windows
req.typenames: HBA_SCSIID, *PHBA_SCSIID
---

# HBA_ScsiId structure


## -description


The HBA_ScsiId structure contains information used by the operating system to identify a SCSI logical unit.


## -syntax


````
typedef struct HBA_ScsiId {
  char       OSDeviceName[256];
  HBA_UINT32 ScsiBusNumber;
  HBA_UINT32 ScsiTargetNumber;
  HBA_UINT32 ScsiOSLun;
} HBA_SCSIID, *PHBA_SCSIID;
````


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

<a href="..\hbaapi\nf-hbaapi-hba_getfcpstatistics.md">HBA_GetFCPStatistics</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [storage\storage]:%20HBA_ScsiId structure%20 RELEASE:%20(1/10/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

