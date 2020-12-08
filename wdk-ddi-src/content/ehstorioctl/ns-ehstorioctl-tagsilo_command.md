---
UID: NS:ehstorioctl.tagSILO_COMMAND
title: tagSILO_COMMAND (ehstorioctl.h)
description: This structure describes a storage silo driver command.
old-location: storage\silo_command.htm
tech.root: storage
ms.date: 03/29/2018
keywords: ["tagSILO_COMMAND structure"]
ms.keywords: "*PSILO_COMMAND, PSILO_COMMAND, PSILO_COMMAND structure pointer [Storage Devices], SILO_COMMAND, SILO_COMMAND structure [Storage Devices], ehstorioctl/PSILO_COMMAND, ehstorioctl/SILO_COMMAND, storage.silo_command, structs-silo_6058ee8b-c6ff-4e84-8b20-304bb6646a4f.xml, tagSILO_COMMAND"
req.header: ehstorioctl.h
req.include-header: EhStorIoctl.h
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
req.typenames: SILO_COMMAND, *PSILO_COMMAND
f1_keywords:
 - tagSILO_COMMAND
 - ehstorioctl/tagSILO_COMMAND
 - PSILO_COMMAND
 - ehstorioctl/PSILO_COMMAND
 - SILO_COMMAND
 - ehstorioctl/SILO_COMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - EhStorIoctl.h
api_name:
 - SILO_COMMAND
---

# tagSILO_COMMAND structure


## -description

This structure describes a storage silo driver command.

## -struct-fields

### -field SiloIndex

### -field Command

This member contains the 1667 command value.

### -field cbCommandBuffer

This member contains the size of the 1667 command buffer.

### -field rgbCommandBuffer

## -remarks

Together, <b>cbCommandBufferSize</b> and <b>rgbCommandBuffer</b> members indicate the raw data payload for the silo command, and are sent as-is to the device. The structure of the data in this buffer is silo-dependent. The structure is assumed to be shared knowledge between the client issuing this IOCTL and the device firmware implementation of this particular silo.

