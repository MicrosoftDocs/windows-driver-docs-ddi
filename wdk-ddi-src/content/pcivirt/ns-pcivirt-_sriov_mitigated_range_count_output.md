---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
title: "_SRIOV_MITIGATED_RANGE_COUNT_OUTPUT"
author: windows-driver-content
description: This structures is the output buffer received by the IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT request that contains an array of ranges of memory-mapped I/O space that must be mitigated.
old-location: pci\sriov_mitigated_range_count_output.htm
tech.root: PCI
ms.assetid: b89c0758-beed-4c29-b966-78cb319258b1
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT, PCI.sriov_mitigated_range_count_output, SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, SRIOV_MITIGATED_RANGE_COUNT_OUTPUT structure [Buses], _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, pcivirt/SRIOV_MITIGATED_RANGE_COUNT_OUTPUT"
ms.topic: struct
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	Pcivirt.h
api_name:
-	SRIOV_MITIGATED_RANGE_COUNT_OUTPUT
product:
- Windows
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, *PSRIOV_MITIGATED_RANGE_COUNT_OUTPUT
---

# _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT structure


## -description


This structures is the output buffer received by the <a href="https://msdn.microsoft.com/68fd97a5-b7ea-43c0-96ed-b64445fd21dd">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a> request that contains an array of ranges of memory-mapped I/O space
 that must be mitigated.


## -syntax


```cpp
typedef struct _SRIOV_MITIGATED_RANGE_COUNT_OUTPUT {
  ULONG [6] RangeCount;
} SRIOV_MITIGATED_RANGE_COUNT_OUTPUT, SRIOV_MITIGATED_RANGE_COUNT_OUTPUT;
```


## -struct-fields




### -field RangeCount

Array of ranges of memory-mapped I/O space
 that must be mitigated.


## -see-also

<a href="https://msdn.microsoft.com/68fd97a5-b7ea-43c0-96ed-b64445fd21dd">IOCTL_SRIOV_QUERY_MITIGATED_RANGE_COUNT</a>



 

 


