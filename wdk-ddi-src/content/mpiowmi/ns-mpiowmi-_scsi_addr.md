---
UID: NS:mpiowmi._SCSI_ADDR
title: "_SCSI_ADDR"
author: windows-driver-content
description: The SCSI_ADDR structure represents a SCSI address.
old-location: storage\scsi_addr.htm
old-project: storage
ms.assetid: d53e0b05-8761-4b88-a7d5-081244b3dc93
ms.author: windowsdriverdev
ms.date: 2/16/2018
ms.keywords: "_SCSI_ADDR, SCSI_ADDR, mpiowmi/PSCSI_ADDR, PSCSI_ADDR structure pointer [Storage Devices], storage.scsi_addr, SCSI_ADDR structure [Storage Devices], structs-scsibus_32f6b726-53af-4ea4-94e2-f30d67811592.xml, mpiowmi/SCSI_ADDR, PSCSI_ADDR, *PSCSI_ADDR"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	mpiowmi.h
apiname:
-	SCSI_ADDR
product: Windows
targetos: Windows
req.typenames: "*PSCSI_ADDR, SCSI_ADDR"
---

# _SCSI_ADDR structure


## -description


The SCSI_ADDR structure represents a SCSI address.


## -syntax


````
typedef struct _SCSI_ADDR {
  UCHAR PortNumber;
  UCHAR ScsiPathId;
  UCHAR TargetId;
  UCHAR Lun;
} SCSI_ADDR, *PSCSI_ADDR;
````


## -struct-fields




### -field PortNumber

An unsigned 8-bitfield that represents the PortNumber as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.


### -field ScsiPathId

An unsigned 8-bitfield that represents the PathId as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.


### -field TargetId

An unsigned 8-bitfield that represents the TargetId as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.


### -field Lun

An unsigned 8-bitfield that represents the Lun as defined by the SCSI_ADDRESS structure in <i>Ntddscsi.h</i>.

