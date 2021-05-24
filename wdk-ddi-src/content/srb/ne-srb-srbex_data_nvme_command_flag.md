---
UID: NE:srb.__unnamed_enum_3
tech.root: storage
title: SRBEX_DATA_NVME_COMMAND_FLAG (srb.h)
ms.date: 05/13/2021
targetos: Windows
description: SRBEX_DATA_NVME_COMMAND_FLAG enumerates the properties of a particular SRBEX Data NVMe command.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: srb.h
req.include-header: 
req.kmdf-ver: 
req.max-support: 
req.target-min-winverclnt:
req.target-min-winversvr: Windows Server 2022
req.target-type: 
req.typenames: 
req.umdf-ver: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - srb.h
api_name:
 - PSRBEX_DATA_NVME_COMMAND_FLAG
 - SRBEX_DATA_NVME_COMMAND_FLAG
f1_keywords:
 - PSRBEX_DATA_NVME_COMMAND_FLAG
 - srb/PSRBEX_DATA_NVME_COMMAND_FLAG
 - SRBEX_DATA_NVME_COMMAND_FLAG
 - srb/SRBEX_DATA_NVME_COMMAND_FLAG
dev_langs:
 - c++
---

## -description

**SRBEX_DATA_NVME_COMMAND_FLAG** enumerates the properties of a particular SRBEX data NVMe command.

## -enum-fields

### -field SRBEX_DATA_NVME_COMMAND_FLAG_REQUIRE_DATA_TRANSFER_IN

Data is being read in from the device. See Remarks.

### -field SRBEX_DATA_NVME_COMMAND_FLAG_REQUIRE_DATA_TRANSFER_OUT

Data is being written out to the device. See Remarks.

### -field SRBEX_DATA_NVME_COMMAND_FLAG_PRP_SET_ALREADY

By default, the system frames a physical region page (PRP) before sending the data transfer command to the device. The user sets this flag if they want to do the framing instead.

### -field SRBEX_DATA_NVME_COMMAND_FLAG_SIGNATURE_ENABLED

Reserved for system use; do not use.

## -remarks

**SRBEX_DATA_NVME_COMMAND_FLAG** can be a bitwise-OR of the above flags.

> [!NOTE]
> Currently, data can only be read OR written in one command (SRBEX_DATA_NVME_COMMAND_FLAG_REQUIRE_DATA_TRANSFER_IN | SRBEX_DATA_NVME_COMMAND_FLAG_REQUIRE_DATA_TRANSFER_OUT).

A user specifies these flags in a [**SRBEX_DATA_NVME_COMMAND**](ns-srb-srbex_data_nvme_command.md) structure.
