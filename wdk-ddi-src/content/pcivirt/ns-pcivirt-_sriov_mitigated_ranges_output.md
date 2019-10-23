---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGES_OUTPUT
title: _SRIOV_MITIGATED_RANGES_OUTPUT (pcivirt.h)
description: This structure is the output buffer received by the IOCTL_SRIOV_QUERY_MITIGATED_RANGES request to get the specific ranges on which intercepts must be placed.
old-location: pci\sriov_mitigated_ranges_output.htm
tech.root: PCI
ms.assetid: f33f602e-0bce-4ac2-8bd8-8640b2376278
ms.date: 02/24/2018
ms.keywords: "*PSRIOV_MITIGATED_RANGES_OUTPUT, PCI.sriov_mitigated_ranges_output, SRIOV_MITIGATED_RANGES_OUTPUT, SRIOV_MITIGATED_RANGES_OUTPUT structure [Buses], _SRIOV_MITIGATED_RANGES_OUTPUT, pcivirt/SRIOV_MITIGATED_RANGES_OUTPUT"
ms.topic: struct
f1_keywords:
 - "pcivirt/SRIOV_MITIGATED_RANGES_OUTPUT"
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
- pcivirt.h
api_name:
- SRIOV_MITIGATED_RANGES_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGES_OUTPUT, *PSRIOV_MITIGATED_RANGES_OUTPUT
---

# _SRIOV_MITIGATED_RANGES_OUTPUT structure


## -description


This structure is the output buffer received by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pcivirt/ni-pcivirt-ioctl_sriov_query_mitigated_ranges">IOCTL_SRIOV_QUERY_MITIGATED_RANGES</a> request to get the specific ranges on which intercepts must be placed.


## -syntax


```cpp
typedef struct _SRIOV_MITIGATED_RANGES_OUTPUT {
  ULONG64  BasePageNumber;
  ULONG    PageCount;
  BOOLEAN  InterceptReads;
  BOOLEAN  InterceptWrites;
} SRIOV_MITIGATED_RANGES_OUTPUT, SRIOV_MITIGATED_RANGES_OUTPUT;
```


## -struct-fields




### -field BasePageNumber

The base address of the allocated region of pages.


### -field PageCount

Total number of pages.


### -field InterceptReads

A boolean that indicates the reads intercept bit.


### -field InterceptWrites

A boolean that indicates the write intercept bit.

