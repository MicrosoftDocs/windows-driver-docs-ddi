---
UID: NS:mpiowmi._SCSI_ADDR
title: _SCSI_ADDR (mpiowmi.h)
description: The SCSI_ADDR structure represents a SCSI address.
old-location: storage\scsi_addr.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["SCSI_ADDR structure"]
ms.keywords: "*PSCSI_ADDR, PSCSI_ADDR, PSCSI_ADDR structure pointer [Storage Devices], SCSI_ADDR, SCSI_ADDR structure [Storage Devices], _SCSI_ADDR, mpiowmi/PSCSI_ADDR, mpiowmi/SCSI_ADDR, storage.scsi_addr, structs-scsibus_32f6b726-53af-4ea4-94e2-f30d67811592.xml"
req.header: mpiowmi.h
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
targetos: Windows
req.typenames: SCSI_ADDR, *PSCSI_ADDR
f1_keywords:
 - _SCSI_ADDR
 - mpiowmi/_SCSI_ADDR
 - PSCSI_ADDR
 - mpiowmi/PSCSI_ADDR
 - SCSI_ADDR
 - mpiowmi/SCSI_ADDR
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - mpiowmi.h
api_name:
 - _SCSI_ADDR
 - PSCSI_ADDR
 - SCSI_ADDR
---

# _SCSI_ADDR structure


## -description

The SCSI_ADDR structure represents a SCSI address.

## -struct-fields

### -field PortNumber

An unsigned 8-bitfield that represents the PortNumber as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.

### -field ScsiPathId

An unsigned 8-bitfield that represents the PathId as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.

### -field TargetId

An unsigned 8-bitfield that represents the TargetId as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.

### -field Lun

An unsigned 8-bitfield that represents the Lun as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.

