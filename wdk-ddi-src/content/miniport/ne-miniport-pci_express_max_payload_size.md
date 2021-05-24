---
UID: NE:miniport.__unnamed_enum_13
tech.root: PCI
title: PCI_EXPRESS_MAX_PAYLOAD_SIZE
ms.date: 05/13/2021
targetos: Windows
description: PCI_EXPRESS_MAX_PAYLOAD_SIZE enumerates the maximum data payload sizes for a PCI Express (PCIe) controller.
req.construct-type: enumeration
req.ddi-compliance: 
req.header: miniport.h
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
 - miniport.h
api_name:
 - PCI_EXPRESS_MAX_PAYLOAD_SIZE
f1_keywords:
 - PCI_EXPRESS_MAX_PAYLOAD_SIZE
 - miniport/PCI_EXPRESS_MAX_PAYLOAD_SIZE
dev_langs:
 - c++
---

## -description

**PCI_EXPRESS_MAX_PAYLOAD_SIZE** enumerates the maximum data payload sizes for a PCI Express (PCIe) controller.

## -enum-fields

### -field MaxPayload128Bytes

The PCIe controller will use a maximum data payload size of 128 bytes.

### -field MaxPayload256Bytes

The PCIe controller will use a maximum data payload size of 256 bytes.

### -field MaxPayload512Bytes

The PCIe controller will use a maximum data payload size of 512 bytes.

### -field MaxPayload1024Bytes

The PCIe controller will use a maximum data payload size of 1024 bytes.

### -field MaxPayload2048Bytes

The PCIe controller will use a maximum data payload size of 2048 bytes.

### -field MaxPayload4096Bytes

The PCIe controller will use a maximum data payload size of 4096 bytes.

## -remarks

**PCI_EXPRESS_MAX_PAYLOAD_SIZE** is reserved for system use.
