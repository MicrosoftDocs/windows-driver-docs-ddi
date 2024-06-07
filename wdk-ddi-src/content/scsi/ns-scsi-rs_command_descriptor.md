---
UID: NS:scsi.RS_COMMAND_DESCRIPTOR
tech.root: storage
title: RS_COMMAND_DESCRIPTOR (scsi.h)
ms.date: 03/21/2024
targetos: Windows
description: The RS_COMMAND_DESCRIPTOR structure contains information about a single supported command descriptor block (CDB).
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
req.typenames: RS_COMMAND_DESCRIPTOR, *PRS_COMMAND_DESCRIPTOR
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
 - RS_COMMAND_DESCRIPTOR
 - PRS_COMMAND_DESCRIPTOR
f1_keywords:
 - RS_COMMAND_DESCRIPTOR
 - scsi/RS_COMMAND_DESCRIPTOR
 - PRS_COMMAND_DESCRIPTOR
 - scsi/PRS_COMMAND_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - RS_COMMAND_DESCRIPTOR
---

## -description

The **RS_COMMAND_DESCRIPTOR** structure contains information about a single supported command descriptor block (CDB).

## -struct-fields

### -field OperationCode

Specifies the command being requested by the command descriptor block (CDB).

### -field Reserved

Reserved for internal use.

### -field ServiceAction[2]

Provides qualification for the *OperationCode* field for some commands, allowing:

- Unrelated commands that share the same operation code, such as the Report Supported Operation Codes and the Report Target Port Groups commands.
- A set of related functions that share the same operation code, for example, the Persistent Reserve In command.

### -field Reserved1

Reserved for internal use.

### -field ServiceActionValid

Indicates that the contents of the *OperationCode* and *ServiceAction* fields are valid.

### -field CommandTimeoutsDescriptorPresent

Indicates that the command timeouts descriptor is included in this command descriptor.

### -field CommandDurationLimitPage

The *ReadWriteCommandDurationLimitsPage* and the *CommandDurationLimitPage* fields together indicate the mode page that specifies the command duration limit for the command.

### -field MultipleLogicalUnits

The *MultipleLogicalUnits* field is described in the following table.

| Value | Description |
|--|--|
| 0 | The effect of this command on other logical units is not reported. |
| 1 | This command only affects this logical unit. |
| 2 | This command affects more than one but not all logical units contained in this SCSI target device. |
| 3 | This command affects all of the logical units contained in this SCSI target device. |

### -field ReadWriteCommandDurationLimitsPage

The *ReadWriteCommandDurationLimitsPage* and the *CommandDurationLimitPage* fields together indicate the mode page that specifies the command duration limit for the command.

### -field Reserved2

Reserved for internal use.

### -field CdbLength[2]

Indicates the length of the command descriptor block in bytes for the *OperationCode*, and if the *ServiceActionValid* is **TRUE**, the action indicated by the *ServiceAction* field.

## -remarks

The values for the *ReadWriteCommandDurationLimitsPage* and the *CommandDurationLimitPage* fields are reflected in the following table.

| ReadWriteCommandDurationLimitsPage | CommandDurationLimitPage | Description |
|--|--|--|
| 0 | 0 | No command duration limit mode page is indicated for this command. |
| 1 | 0 | Reserved |
| 0 | 1 | Command duration limit A mode page |
| 0 | 2 | Command duration limit B mode page |
| 1 | 1 | Command duration limit T2A mode page |
| 1 | 2 | Command duration limit T2B mode page |
| 0 or 1 | 3 | Reserved |

## -see-also
