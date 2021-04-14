---
UID: NS:srb._SRBEX_DATA_NVME_COMMAND
tech.root: storage
title: SRBEX_DATA_NVME_COMMAND
ms.date: 05/13/2021
targetos: Windows
description: The SRBEX_DATA_NVME_COMMAND structure enables the user to frame and issue a command in NVMe format.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: srb.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 21H1
req.target-min-winversvr: 
req.target-type: 
req.typenames: SRBEX_DATA_NVME_COMMAND, *PSRBEX_DATA_NVME_COMMAND
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - srb.h
api_name:
 - _SRBEX_DATA_NVME_COMMAND
 - PSRBEX_DATA_NVME_COMMAND
 - SRBEX_DATA_NVME_COMMAND
f1_keywords:
 - _SRBEX_DATA_NVME_COMMAND
 - srb/_SRBEX_DATA_NVME_COMMAND
 - PSRBEX_DATA_NVME_COMMAND
 - srb/PSRBEX_DATA_NVME_COMMAND
 - SRBEX_DATA_NVME_COMMAND
 - srb/SRBEX_DATA_NVME_COMMAND
dev_langs:
 - c++
---

## -description

The **SRBEX_DATA_NVME_COMMAND** structure enables the user to frame and issue a command in NVMe format. This structure is currently reserved for system use.

## -struct-fields

### -field Type

Command type. Currently this must be set to **SrbExDataTypeNvmeCommand**.

### -field Length

Size of this structure, in bytes.

### -field CommandDWORD0

Command Dword 0 within the NVMe command (see the NVMe specification).

### -field CommandNSID

Namespace identifier within the NVMe command (see the NVMe specification).

### -field Reserved0

Reserved; do not use.

### -field CommandMPTR

Metadata pointer within the NVMe command (see the NVMe specification).

### -field CommandPRP1

Physical region page (PRP) Entry 1 within the NVMe command (see the NVMe spec). To indicate that PRP information is present, the user must set the **SRBEX_DATA_NVME_COMMAND_FLAG_PRP_SET_ALREADY** flag of [**SRBEX_DATA_NVME_COMMAND_FLAG**](ne-srb-srbex_data_nvme_command_flag.md).

### -field CommandPRP2

PRP Entry 2 within the NVMe command (see the NVMe spec). To indicate that PRP information is present, the user must set the **SRBEX_DATA_NVME_COMMAND_FLAG_PRP_SET_ALREADY** flag of [**SRBEX_DATA_NVME_COMMAND_FLAG**](ne-srb-srbex_data_nvme_command_flag.md).

### -field CommandCDW10

Command-specific Dword 10 (see the NVMe spec).

### -field CommandCDW11

Command-specific Dword 11 (see the NVMe spec).

### -field CommandCDW12

Command-specific Dword 12 (see the NVMe spec).

### -field CommandCDW13

Command-specific Dword 13 (see the NVMe spec).

### -field CommandCDW14

Command-specific Dword 14 (see the NVMe spec).

### -field CommandCDW15

Command-specific Dword 15 (see the NVMe spec).

### -field CommandType

A [**SRBEX_DATA_NVME_COMMAND_TYPE**](ne-srb-srbex_data_nvme_command_type.md) value that specifies the NVMe command type.

### -field CommandFlags

A [**SRBEX_DATA_NVME_COMMAND_FLAG**](ne-srb-srbex_data_nvme_command_flag.md) value that specifies the properties of this SRBEX data NVMe command.

### -field CommandStatus

Status field from the Completion Queue entry (see the NVMe spec).

### -field CommandStatus.DUMMYSTRUCTNAME

### -field CommandStatus.DUMMYSTRUCTNAME.P

Phase tag (P).

### -field CommandStatus.DUMMYSTRUCTNAME.SC

Status code (SC).

### -field CommandStatus.DUMMYSTRUCTNAME.SCT

Status code type (SCT).

### -field CommandStatus.DUMMYSTRUCTNAME.Reserved

Reserved.

### -field CommandStatus.DUMMYSTRUCTNAME.M

More (M).

### -field CommandStatus.DUMMYSTRUCTNAME.DNR

Do not retry (DNR).

### -field CommandStatus.AsUshort

### -field QID

User-specified queue ID (see the NVMe spec). If unspecified, set this value to 0xFFFFFFFF.

### -field CommandTag

Unique, user-specified identifier for the command identifier to mark a specific command. A user can use **CommandTag** to trace the result of the command in an Event Tracing for Windows (ETW) trace (for example, in Event Viewer's Storage log).

## -remarks

## -see-also

[**SRBEX_DATA_NVME_COMMAND_FLAG**](ne-srb-srbex_data_nvme_command_flag.md)

[**SRBEX_DATA_NVME_COMMAND_FLAG**](ne-srb-srbex_data_nvme_command_flag.md)
