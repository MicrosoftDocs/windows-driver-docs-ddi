---
UID: NS:scsi.PRI_REPORT_CAPABILITIES
tech.root: storage
title: PRI_REPORT_CAPABILITIES (scsi.h)
ms.date: 03/21/2024
targetos: Windows
description: The PRI_REPORT_CAPABILITIES structure contains information on persistent reservation features.
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
req.typenames: PRI_REPORT_CAPABILITIES, *PPRI_REPORT_CAPABILITIES
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
 - PRI_REPORT_CAPABILITIES
 - PPRI_REPORT_CAPABILITIES
f1_keywords:
 - PRI_REPORT_CAPABILITIES
 - scsi/PRI_REPORT_CAPABILITIES
 - PPRI_REPORT_CAPABILITIES
 - scsi/PPRI_REPORT_CAPABILITIES
dev_langs:
 - c++
helpviewer_keywords:
 - PRI_REPORT_CAPABILITIES
---

## -description

The **PRI_REPORT_CAPABILITIES** structure contains the information on persistent reservation features that is returned in response to a Persistent Reserve In command with `ServiceAction=RESERVATION_ACTION_REPORT_CAPABILITIES`.

## -struct-fields

### -field Length[2]

The size of this structure.

### -field PersistThroughPowerLossCapable

Indicates that the device server supports persisting through a power loss event.

### -field Reserved

Reserved for internal use.

### -field AllTargetPortsCapable

Indicates that the device server supports all target ports.

### -field SpecifyInitiatorPortsCapable

Indicates that the device server supports specifying initiator ports.

### -field CompatibleReservationHandling

Indicates that the device server is backward compatible with SPC-2.

### -field Reserved1

Reserved for internal use.

### -field ReplaceLostReservationCapable

Indicates that the device server supports replacing a lost reservation.

### -field PersistThroughPowerLossActivated

Indicates that the persist through power loss capability is activated.

### -field Reserved2

Reserved for internal use.

### -field AllowCommands

Indicates whether certain commands are allowed through certain types of persistent reservations.

| Value | Description |
|--|--|
| 0 | No information is provided about whether certain commands are allowed through certain types of persistent reservations. |
| 1 | The device server allows the TEST UNIT READY command through write exclusive type reservations and exclusive access type reservations. The device server does not provide information about whether the following commands are allowed through Write Exclusive type reservations: <ol><li>MODE SENSE</li><li>READ ATTRIBUTE</li><li>READ BUFFER(10)</li><li>RECEIVE DIAGNOSTIC RESULTS</li><li>REPORT SUPPORTED OPERATION CODES</li><li>REPORT SUPPORTED TASK MANAGEMENT FUNCTIONS</li><li>READ DEFECT DATA</li></ol> |
| 2 | The device server allows the TEST UNIT READY command through write exclusive type reservations and exclusive access type reservations. The device server does not allow the following commands through Write Exclusive type reservations: <ol><li>MODE SENSE</li><li>READ ATTRIBUTE</li><li>READ BUFFER(10)</li><li>RECEIVE DIAGNOSTIC RESULTS</li><li>REPORT SUPPORTED OPERATION CODES</li><li>REPORT SUPPORTED TASK MANAGEMENT FUNCTIONS</li><li>READ DEFECT DATA</li></ol> |
| 3 | The device server allows the TEST UNIT READY command through write exclusive and exclusive access type reservations. And the following commands through write exclusive type reservations:<ol><li>MODE SENSE</li><li>READ ATTRIBUTE</li><li>READ BUFFER(10)</li><li>RECEIVE DIAGNOSTIC RESULTS</li><li>REPORT SUPPORTED OPERATION CODES</li><li>REPORT SUPPORTED TASK MANAGEMENT FUNCTIONS</li><li>READ DEFECT DATA</li></ol> |
| 4 | The device server allows the TEST UNIT READY command through write exclusive and exclusive access persistent reservations. And the following commands through write exclusive persist reservations:<ol><li>MODE SENSE</li><li>READ ATTRIBUTE</li><li>READ BUFFER(10)</li><li>RECEIVE DIAGNOSTIC RESULTS</li><li>REPORT SUPPORTED OPERATION CODES</li><li>REPORT SUPPORTED TASK MANAGEMENT FUNCTIONS</li><li>READ DEFECT DATA</li></ol> |
| 5 | The device server allows:<ol><li>The following commands through write exclusive and exclusive access persistent reservations:<ol><li>TEST UNIT READY</li><li>REPORT SUPPORTED OPERATION CODES</li><li>REPORT SUPPORTED TASK MANAGEMENT FUNCTIONS</li></ol></li><li>The following commands through write exclusive persistent reservations:<ol><li>MODE SENSE</li><li>READ ATTRIBUTE</li><li>READ BUFFER(10)</li><li>RECEIVE DIAGNOSTIC RESULTS</li><li>READ DEFECT DATA</li></ol></li></ol> |
| All others | Reserved |

### -field TypeMaskValid

Contains a bitmask that indicates the persistent reservation types that are supported by the device server.

### -field Reserved3

Reserved for internal use.

### -field WriteExclusive

Indicates that the device server supports the write exclusive persistent reservation type.

### -field Reserved4

Reserved for internal use.

### -field ExclusiveAccess

Indicates that the device server supports the exclusive access persistent reservation type.

### -field Reserved5

Reserved for internal use.

### -field WriteExclusiveRegistrantsOnly

Indicates that the device server supports the write exclusive – registrants only persistent reservation type.

### -field ExclusiveAccessRegistrantsOnly

Indicates that the device server supports the exclusive access – registrants only persistent reservation type.

### -field WriteExclusiveAllRegistrants

Indicates that the device server supports the write exclusive – all registrants persistent reservation type.

### -field ExclusiveAccessAllRegistrants

Indicates that the device server supports the exclusive access – all registrants persistent reservation type.

### -field Reserved6

Reserved for internal use.

### -field Reserved7[2]

Reserved for internal use.

## -remarks

## -see-also
