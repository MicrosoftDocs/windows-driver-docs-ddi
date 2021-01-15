---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
title: _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT (pcivirt.h)
description: This structures is the output buffer received by the IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT request that contains an array of ranges of memory-mapped I/O space that must be mitigated.
old-location: pci\sriov_mitigated_range_count_output.htm
tech.root: PCI
ms.date: 02/24/2018
keywords: ["SRIOV_MITIGATED_RANGE_COUNT_OUTPUT structure"]
ms.keywords: "*PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT, PCI.sriov_mitigated_range_count_output, SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, SRIOV_MITIGATED_RANGE_COUNT_OUTPUT structure [Buses], _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, pcivirt/SRIOV_MITIGATED_RANGE_COUNT_OUTPUT"
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
req.typenames: SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, *PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT
f1_keywords:
 - _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - pcivirt/_SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - pcivirt/PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - pcivirt/SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Pcivirt.h
api_name:
 - _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT
 - SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
---

# _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT structure


## -description

This structures is the output buffer received by the <a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_range_count">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> request that contains an array of ranges of memory-mapped I/O space
 that must be mitigated.

## -struct-fields

### -field RangeCount

Array of ranges of memory-mapped I/O space
 that must be mitigated.

## -syntax

```cpp
typedef struct _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT {
  ULONG [6] RangeCount;
} SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, SRIOV_MITIGATED_RANGE_COUNT_OUTPUT;
```

## -see-also

<a href="/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_range_count">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a>

