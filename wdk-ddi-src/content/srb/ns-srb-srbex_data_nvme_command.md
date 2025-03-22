---
UID: NS:srb._SRBEX_DATA_NVME_COMMAND
tech.root: storage
title: SRBEX_DATA_NVME_COMMAND (srb.h)
ms.date: 02/21/2024
targetos: Windows
description: The SRBEX_DATA_NVME_COMMAND (srb.h) structure enables the user to frame and issue a command in NVMe format.
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: srb.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
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

# SRBEX_DATA_NVME_COMMAND structure (srb.h)

## -description

The **SRBEX_DATA_NVME_COMMAND** structure enables the user to frame and issue a command in NVMe format. This structure is currently reserved for system use.

## -struct-fields

### -field Type

Command type. Currently this must be set to **SrbExDataTypeNvmeCommand**.

### -field Length

Size of this structure, in bytes.

### -field ControllerHandle

Miniport's handle for the NVMe controller.

### -field Reserved0

Reserved; do not use.

### -field CommandDWORD0

Command Dword 0 within the NVMe command (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandNSID

Namespace identifier within the NVMe command (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field Reserved1[2]

Reserved; do not use.

### -field CommandMPTR

Metadata pointer within the NVMe command (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandPRP1

Physical region page (PRP) Entry 1 within the NVMe command (see the [NVMe specifications](https://nvmexpress.org/specifications/)). To indicate that PRP information is present, the user must set the **SRBEX_DATA_NVME_COMMAND_FLAG_PRP_SET_ALREADY** flag of **[SRBEX_DATA_NVME_COMMAND_FLAG](ne-srb-srbex_data_nvme_command_flag.md)**.

### -field CommandPRP2

PRP Entry 2 within the NVMe command (see the [NVMe specifications](https://nvmexpress.org/specifications/)). To indicate that PRP information is present, the user must set the **SRBEX_DATA_NVME_COMMAND_FLAG_PRP_SET_ALREADY** flag of **[SRBEX_DATA_NVME_COMMAND_FLAG](ne-srb-srbex_data_nvme_command_flag.md)**.

### -field CommandSGL1[2]

Command-specific scatter gather list (SGL) Entry 1 field (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandCDW10

Command-specific Dword 10 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandCDW11

Command-specific Dword 11 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandCDW12

Command-specific Dword 12 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandCDW13

Command-specific Dword 13 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandCDW14

Command-specific Dword 14 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandCDW15

Command-specific Dword 15 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field FabricsCommand

**NVMEOF_FABRICS_COMMAND** in nvme.h

### -field FabricsCommand.OPC

Opcode (7Fh).

### -field FabricsCommand.PSDT

PRP or SGL for data transfer. (only bits 7:6 are used, the rest are reserved).

### -field FabricsCommand.CID

Fabrics command identifier.

### -field FabricsCommand.FCTYPE

Fabrics command type.

### -field FabricsCommand.Reserved[35]

Reserved; do not use.

### -field FabricsCommand.Specific[24]

Command type specific (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field Command

To reference command DW0 (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field Command.OPC

Opcode (OPC).

### -field Command.FUSE

Fused Operation (FUSE).

### -field Command.Reserved

Reserved; do not use.

### -field Command.PSDT

PRP or SGL for data transfer.

### -field Command.CID

Command identifier.

### -field Command.TypeSpecific[60]

Command type specific (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandType

A **[SRBEX_DATA_NVME_COMMAND_TYPE](ne-srb-srbex_data_nvme_command_type.md)** value that specifies the NVMe command type.

### -field Reserved2

Reserved; do not use.

### -field CommandFlags

A **[SRBEX_DATA_NVME_COMMAND_FLAG](ne-srb-srbex_data_nvme_command_flag.md)** value that specifies the properties of this SRBEX data NVMe command.

### -field ResponseFlags

Defined in [SRBEX_DATA_NVME_RESPONSE_FLAG](ne-srb-srbex_data_nvme_response_flag.md).

### -field CommandStatus

Status field from the Completion Queue entry (see the [NVMe specifications](https://nvmexpress.org/specifications/)).

### -field CommandStatus.DUMMYSTRUCTNAME

Embedded structure.

### -field CommandStatus.DUMMYSTRUCTNAME.P

Phase tag (P).

### -field CommandStatus.DUMMYSTRUCTNAME.SC

Status code (SC).

### -field CommandStatus.DUMMYSTRUCTNAME.SCT

Status code type (SCT).

### -field CommandStatus.DUMMYSTRUCTNAME.CRD

Command retry delay (CRD).

### -field CommandStatus.DUMMYSTRUCTNAME.M

More (M).

### -field CommandStatus.DUMMYSTRUCTNAME.DNR

Do not retry (DNR).

### -field CommandStatus.AsUshort

### -field QID

User-specified queue ID (see the [NVMe specifications](https://nvmexpress.org/specifications/)). If unspecified, set this value to 0xFFFFFFFF.

### -field CommandTag

Unique, user-specified identifier for the command identifier to mark a specific command. A user can use **CommandTag** to trace the result of the command in an Event Tracing for Windows (ETW) trace (for example, in Event Viewer's Storage log).

### -field CQEntryDW0

Completion queue entry DW0.

### -field CQEntryDW1

Completion queue entry DW1.

### -field Specific[8]

Fabrics command specific response.

### -field SQHD

SQ head pointer in completion queue entry.

### -field SQID

SQ identifier.

## -remarks

## -see-also

- **[SRBEX_DATA_NVME_COMMAND_FLAG](ne-srb-srbex_data_nvme_command_flag.md)**
- **[SRBEX_DATA_NVME_COMMAND_FLAG](ne-srb-srbex_data_nvme_command_flag.md)**
- [NVMe specifications](https://nvmexpress.org/specifications/)
