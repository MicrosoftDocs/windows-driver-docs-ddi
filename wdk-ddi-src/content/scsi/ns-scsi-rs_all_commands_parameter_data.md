---
UID: NS:scsi.RS_ALL_COMMANDS_PARAMETER_DATA
tech.root: storage
title: RS_ALL_COMMANDS_PARAMETER_DATA (scsi.h)
ms.date: 03/21/2024
targetos: Windows
description: The RS_ALL_COMMANDS_PARAMETER_DATA structure contains a list of RS_COMMAND_DESCRIPTOR structures.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: scsi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: RS_ALL_COMMANDS_PARAMETER_DATA, *PRS_ALL_COMMANDS_PARAMETER_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - scsi.h
api_name:
 - RS_ALL_COMMANDS_PARAMETER_DATA
 - PRS_ALL_COMMANDS_PARAMETER_DATA
f1_keywords:
 - RS_ALL_COMMANDS_PARAMETER_DATA
 - scsi/RS_ALL_COMMANDS_PARAMETER_DATA
 - PRS_ALL_COMMANDS_PARAMETER_DATA
 - scsi/PRS_ALL_COMMANDS_PARAMETER_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - RS_ALL_COMMANDS_PARAMETER_DATA
---

## -description

The **RS_ALL_COMMANDS_PARAMETER_DATA** structure contains a list of **[RS_COMMAND_DESCRIPTOR](ns-scsi-rs_command_descriptor.md)** structures.

## -struct-fields

### -field CommandDataLength[4]

The length of this structure.

### -field CommandDescriptor[ANYSIZE_ARRAY]

An array of **[RS_COMMAND_DESCRIPTOR](ns-scsi-rs_command_descriptor.md)** structures.

## -remarks

## -see-also
