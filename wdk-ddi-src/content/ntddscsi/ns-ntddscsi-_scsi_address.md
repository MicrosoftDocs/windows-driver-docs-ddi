---
UID: NS:ntddscsi._SCSI_ADDRESS
title: _SCSI_ADDRESS (ntddscsi.h)
description: The SCSI_ADDRESS structure is used in conjunction with the IOCTL_SCSI_GET_ADDRESS request to retrieve the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target.
old-location: storage\scsi_address.htm
tech.root: storage
ms.assetid: 2b3acd3d-b5da-4dd3-89f1-0b8a7d68e54c
ms.date: 03/29/2018
ms.keywords: "*PSCSI_ADDRESS, PSCSI_ADDRESS, PSCSI_ADDRESS structure pointer [Storage Devices], SCSI_ADDRESS, SCSI_ADDRESS structure [Storage Devices], _SCSI_ADDRESS, ntddscsi/PSCSI_ADDRESS, ntddscsi/SCSI_ADDRESS, storage.scsi_address, structs-scsibus_6b7a15bf-09f3-4fe2-bbef-77e1fd6e1744.xml"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- ntddscsi.h
api_name:
- SCSI_ADDRESS
product:
- Windows
targetos: Windows
req.typenames: SCSI_ADDRESS, *PSCSI_ADDRESS
---

# _SCSI_ADDRESS structure


## -description


The SCSI_ADDRESS structure is used in conjunction with the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560500">IOCTL_SCSI_GET_ADDRESS</a> request to retrieve the address information, such as the target ID (TID) and the logical unit number (LUN) of a particular SCSI target. 
<div class="alert"><b>Note</b>  The SCSI port driver and SCSI miniport driver models may be altered or unavailable in the future. Instead, we recommend using the <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-driver">Storport driver</a> and <a href="https://msdn.microsoft.com/windows/hardware/drivers/storage/storport-miniport-drivers">Storport miniport</a> driver models.</div><div> </div>

## -struct-fields




### -field Length

Contains the length of this structure in bytes. 


### -field PortNumber

Contains the number of the SCSI adapter.


### -field PathId

Contains the number of the bus. 


### -field TargetId

Contains the number of the target device. 


### -field Lun

Contains the logical unit number.


## -remarks



Legacy class drivers issue the <a href="https://msdn.microsoft.com/library/windows/hardware/ff560500">IOCTL_SCSI_GET_ADDRESS</a> request to the port driver to obtain the address of their devices. 




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff560500">IOCTL_SCSI_GET_ADDRESS</a>
 

 

