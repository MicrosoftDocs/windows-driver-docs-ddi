---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_COUNT_INPUT
title: _SRIOV_MITIGATED_RANGE_COUNT_INPUT (pcivirt.h)
description: This structure is used as an input buffer to the IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT request to determine the ranges of memory-mapped I/O space that must be mitigated.
old-location: pci\sriov_mitigated_range_count_input.htm
tech.root: PCI
ms.assetid: 7de35a35-2b90-421d-bbde-4c5cb760070a
ms.date: 02/24/2018
keywords: ["SRIOV_MITIGATED_RANGE_COUNT_INPUT structure"]
ms.keywords: "*PSRIOV_MITIGATED_RANGE_COUNT_INPUT, PCI.sriov_mitigated_range_count_input, SRIOV_MITIGATED_RANGE_COUNT_INPUT, SRIOV_MITIGATED_RANGE_COUNT_INPUT structure [Buses], _SRIOV_MITIGATED_RANGE_COUNT_INPUT, pcivirt/SRIOV_MITIGATED_RANGE_COUNT_INPUT"
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
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGE_COUNT_INPUT, *PSRIOV_MITIGATED_RANGE_COUNT_INPUT
f1_keywords:
 - _SRIOV_MITIGATED_RANGE_COUNT_INPUT
 - pcivirt/_SRIOV_MITIGATED_RANGE_COUNT_INPUT
 - PSRIOV_MITIGATED_RANGE_COUNT_INPUT
 - pcivirt/PSRIOV_MITIGATED_RANGE_COUNT_INPUT
 - SRIOV_MITIGATED_RANGE_COUNT_INPUT
 - pcivirt/SRIOV_MITIGATED_RANGE_COUNT_INPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - SRIOV_MITIGATED_RANGE_COUNT_INPUT
---

# _SRIOV_MITIGATED_RANGE_COUNT_INPUT structure


## -description

This structure is used as an input buffer to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_range_count">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> request to determine the ranges of memory-mapped I/O space that must be mitigated.

## -struct-fields

### -field VfIndex

Zero-based index of the virtual function from the first virtual function exposed by this physical function.

## -syntax

```cpp
typedef struct _SRIOV_MITIGATED_RANGE_COUNT_INPUT {
  USHORT  VfIndex;
} SRIOV_MITIGATED_RANGE_COUNT_INPUT, SRIOV_MITIGATED_RANGE_COUNT_INPUT;
```

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_range_count">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a>

