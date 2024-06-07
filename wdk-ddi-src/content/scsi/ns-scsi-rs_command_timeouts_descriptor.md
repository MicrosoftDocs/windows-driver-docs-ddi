---
UID: NS:scsi.RS_COMMAND_TIMEOUTS_DESCRIPTOR
tech.root: storage
title: RS_COMMAND_TIMEOUTS_DESCRIPTOR (scsi.h)
ms.date: 03/21/2024
targetos: Windows
description: The RS_COMMAND_TIMEOUTS_DESCRIPTOR structure contains command timeout information from the start of processing a command to its reported completion.
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
req.typenames: RS_COMMAND_TIMEOUTS_DESCRIPTOR, *PRS_COMMAND_TIMEOUTS_DESCRIPTOR
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
 - RS_COMMAND_TIMEOUTS_DESCRIPTOR
 - PRS_COMMAND_TIMEOUTS_DESCRIPTOR
f1_keywords:
 - RS_COMMAND_TIMEOUTS_DESCRIPTOR
 - scsi/RS_COMMAND_TIMEOUTS_DESCRIPTOR
 - PRS_COMMAND_TIMEOUTS_DESCRIPTOR
 - scsi/PRS_COMMAND_TIMEOUTS_DESCRIPTOR
dev_langs:
 - c++
helpviewer_keywords:
 - RS_COMMAND_TIMEOUTS_DESCRIPTOR
---

## -description

The **RS_COMMAND_TIMEOUTS_DESCRIPTOR** structure contains command timeout information from the start of processing a command to its reported completion.

## -struct-fields

### -field DescriptorLength[2]

The length of this structure.

### -field Reserved

Reserved for internal use.

### -field CommandSpecific

Contains timeout information defined for a specific command, such as the write buffer command.

### -field NominalCommandProcessingTimeoutInSec[4]

Indicates the minimum amount of time, in seconds, that the application client should wait before checking the progress of the command. A value of zero means that no timeout is specified.

### -field RecommendedCommandTimeoutInSec[4]

Specifies the recommended time, in seconds, that the application client should wait before timing out the command. A value of zero means that no time is specified.

## -remarks

Values contained in the command timeouts descriptor do not include times that are outside the control of the device server.

For commands that cause a change in power condition, values contained in the command timeouts descriptor do not include transition time.

## -see-also
