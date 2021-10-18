---
UID: NE:srb.__unnamed_enum_2
tech.root: storage
title: SRBEX_DATA_NVME_COMMAND_TYPE (srb.h)
ms.date: 05/13/2021
targetos: Windows
description: The SRBEX_DATA_NVME_COMMAND_TYPE (srb.h) contains values that indicate the SRBEX Data NVMe command types.
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
 - PSRBEX_DATA_NVME_COMMAND_TYPE
 - SRBEX_DATA_NVME_COMMAND_TYPE
f1_keywords:
 - PSRBEX_DATA_NVME_COMMAND_TYPE
 - srb/PSRBEX_DATA_NVME_COMMAND_TYPE
 - SRBEX_DATA_NVME_COMMAND_TYPE
 - srb/SRBEX_DATA_NVME_COMMAND_TYPE
dev_langs:
 - c++
---

## -description

**SRBEX_DATA_NVME_COMMAND_TYPE** enumerates the NVMe command types.

## -enum-fields

### -field SRBEX_DATA_NVME_COMMAND_TYPE_NVM

The command is an NVM command.

### -field SRBEX_DATA_NVME_COMMAND_TYPE_ADMIN

The command is an Admin command.

## -remarks

**SRBEX_DATA_NVME_COMMAND_TYPE** is specified in a [**SRBEX_DATA_NVME_COMMAND**](ns-srb-srbex_data_nvme_command.md) structure.
