---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
title: _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT (pcivirt.h)
description: This structures is the output buffer received by the IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request that indicates the virtual function (VF) whose memory-mapped I/O space was mitigated.
old-location: pci\sriov_mitigated_range_update_output.htm
tech.root: PCI
ms.assetid: bd72ac9a-2985-4f2d-8b72-4039c9d3f896
ms.date: 02/24/2018
keywords: ["SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT structure"]
ms.keywords: "*PSRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, PCI.sriov_mitigated_range_update_output, SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT structure [Buses], _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, pcivirt/SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT"
f1_keywords:
 - "pcivirt/SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT"
 - "SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT"
req.header: pcivirt.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.ddi-compliance:
req.unicode-ansi:
req.idl:
req.max-support:
req.namespace:
req.assembly:
req.type-library:
req.lib:
req.dll:
req.irql: PASSIVE_LEVEL
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- Pcivirt.h
api_name:
- SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, *PSRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
---

# _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT structure


## -description


This structures is the output buffer received by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_mitigated_range_update">IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</a> request that indicates the virtual function (VF) whose memory-mapped I/O space
 was mitigated.


## -syntax


```cpp
typedef struct _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT {
  USHORT  VfIndex;
} SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT;
```


## -struct-fields




### -field VfIndex

Zero-based index of the virtual function from the first virtual function exposed by this physical function.

