---
UID: NS:storport.RS_ONE_COMMAND_PARAMETER_DATA
tech.root: storage
title: RS_ONE_COMMAND_PARAMETER_DATA (storport.h)
ms.date: 03/22/2024
targetos: Windows
description: The RS_ONE_COMMAND_PARAMETER_DATA structure contains information about the command data block (CDB) and a usage map for bits in the CDB.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: storport.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.target-type: 
req.typenames: RS_ONE_COMMAND_PARAMETER_DATA, *PRS_ONE_COMMAND_PARAMETER_DATA
typedef_isUnnamed: true
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - storport.h
api_name:
 - RS_ONE_COMMAND_PARAMETER_DATA
 - PRS_ONE_COMMAND_PARAMETER_DATA
f1_keywords:
 - RS_ONE_COMMAND_PARAMETER_DATA
 - storport/RS_ONE_COMMAND_PARAMETER_DATA
 - PRS_ONE_COMMAND_PARAMETER_DATA
 - storport/PRS_ONE_COMMAND_PARAMETER_DATA
dev_langs:
 - c++
helpviewer_keywords:
 - RS_ONE_COMMAND_PARAMETER_DATA
---

## -description

The **RS_ONE_COMMAND_PARAMETER_DATA** structure contains information about the command data block (CDB) and a usage map for bits in the CDB.

## -struct-fields

### -field ReadWriteCommandDurationLimitsPage

Indicates the mode page, if any, that specifies the duration limit for the command.

### -field Reserved

Reserved for internal use.

### -field Support

The *Support* field values are described in the following table:

| Value | Description |
|--|--|
| 0 | Data about the requested command is not currently available. No data after byte one is valid. A subsequent request for command support data may be successful. |
| 1 | The device server does not support the requested command. Data after byte one is undefined. |
| 2 | Reserved |
| 3 | The device server supports the requested command in conformance with a standard. |
| 4 | Reserved |
| 5 | The device server supports the requested command in a vendor specific manner. |
| 6-7 | Reserved |

### -field CommandDurationLimitPage

Specified the command duration limit page mode. For more information see **[RS_COMMAND_DESCRIPTOR](ns-storport-rs_command_descriptor.md)**.

### -field MultipleLogicalUnits

The *MultipleLogicalUnits* field values are described in the following table:

| Value | Description |
|--|--|
| 0 | The effect of this command on other logical units is not reported. |
| 1 | This command affects only this logical unit. |
| 2 | This command affects more than one, but not all, logical units contained in this target device. |
| 3 | This command affects all of the logical units contained in this target device. |

### -field CommandTimeoutsDescriptorPresent

Indicates that the command timeouts descriptor is included in the command descriptor.

### -field CdbSize[2]

The size of the command data block (CDB).

### -field CdbUsageData[ANYSIZE_ARRAY]

A bit field containing information about the command data block (CDB). The first byte contains the operation code. If the command contains a service action, that code is in the *CdbUsageData* field in the same location as the *ServiceAction* field of the command CDB. All other bytes of the *CdbUsageData* field contain a usage map for bits in the command data block.

## -remarks

## -see-also

- **[RS_COMMAND_DESCRIPTOR](ns-storport-rs_command_descriptor.md)**
