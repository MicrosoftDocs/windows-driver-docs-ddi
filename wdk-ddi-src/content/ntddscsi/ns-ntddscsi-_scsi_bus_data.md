---
UID: NS:ntddscsi._SCSI_BUS_DATA
title: "_SCSI_BUS_DATA"
author: windows-driver-content
description: The SCSI_BUS_DATA structure is used in conjunction with the IOCTL_SCSI_GET_INQUIRY_DATA request and the SCSI_ADAPTER_BUS_INFO structure to retrieve the SCSI inquiry data for all devices on a given SCSI bus.
old-location: storage\scsi_bus_data.htm
old-project: storage
ms.assetid: d7baddb5-ad12-4aea-9515-97511dc05fe7
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*PSCSI_BUS_DATA, PSCSI_BUS_DATA, PSCSI_BUS_DATA structure pointer [Storage Devices], SCSI_BUS_DATA, SCSI_BUS_DATA structure [Storage Devices], _SCSI_BUS_DATA, ntddscsi/PSCSI_BUS_DATA, ntddscsi/SCSI_BUS_DATA, storage.scsi_bus_data, structs-scsibus_8a0f86c6-4011-4c11-90e8-bf3c28a147dc.xml"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: ntddscsi.h
req.include-header: Ntddscsi.h
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
-	ntddscsi.h
api_name:
-	SCSI_BUS_DATA
product: Windows
targetos: Windows
req.typenames: SCSI_BUS_DATA, *PSCSI_BUS_DATA
---

# _SCSI_BUS_DATA structure


## -description


The SCSI_BUS_DATA structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560509">IOCTL_SCSI_GET_INQUIRY_DATA</a> request and the <a href="https://msdn.microsoft.com/library/windows/hardware/ff564949">SCSI_ADAPTER_BUS_INFO</a> structure to retrieve the SCSI inquiry data for all devices on a given SCSI bus. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/en-us/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field NumberOfLogicalUnits

Contains the number of logical units on the bus for which inquiry data is being retrieved. 


### -field InitiatorBusId

Contains the SCSI bus ID for the adapter. 


### -field InquiryDataOffset

Contains an offset from the beginning of the SCSI_ADAPTER_BUS_INFO structure to the inquiry data.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560509">IOCTL_SCSI_GET_INQUIRY_DATA</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff564949">SCSI_ADAPTER_BUS_INFO</a>
 

 

