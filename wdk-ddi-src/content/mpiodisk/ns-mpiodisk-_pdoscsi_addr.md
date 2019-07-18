---
UID: NS:mpiodisk._PDOSCSI_ADDR
title: _PDOSCSI_ADDR (mpiodisk.h)
description: The PDOSCSI_ADDR structure is used to represent a SCSI address.
old-location: storage\pdoscsi_addr.htm
tech.root: storage
ms.assetid: ad31cff9-06bd-4c3a-b1e1-5a82cc6b48a2
ms.date: 03/29/2018
ms.keywords: "*PPDOSCSI_ADDR, PDOSCSI_ADDR, PDOSCSI_ADDR structure [Storage Devices], PPDOSCSI_ADDR, PPDOSCSI_ADDR structure pointer [Storage Devices], _PDOSCSI_ADDR, mpiodisk/PDOSCSI_ADDR, mpiodisk/PPDOSCSI_ADDR, storage.pdoscsi_addr, structs-scsibus_4875cdbd-eeff-447f-b682-a2ab41196146.xml"
ms.topic: struct
f1_keywords:
 - "mpiodisk/PDOSCSI_ADDR"
req.header: mpiodisk.h
req.include-header: Mpiowmi.h
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
- mpiodisk.h
api_name:
- PDOSCSI_ADDR
product:
- Windows
targetos: Windows
req.typenames: PDOSCSI_ADDR, *PPDOSCSI_ADDR
---

# _PDOSCSI_ADDR structure


## -description


The PDOSCSI_ADDR structure is used to represent a SCSI address.


## -struct-fields




### -field PortNumber

An unsigned 8-bitfield that represents the PortNumber as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.


### -field ScsiPathId

An unsigned 8-bitfield that represents the PathId as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.


### -field TargetId

An unsigned 8-bitfield that represents the TargetId as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.


### -field Lun

An unsigned 8-bitfield that represents the Lun as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.

