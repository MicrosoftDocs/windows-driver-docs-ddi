---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_UPDATE_INPUT
title: "_SRIOV_MITIGATED_RANGE_UPDATE_INPUT"
author: windows-driver-content
description: This structure is used as an input buffer to the IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request to indicate the virtual function (VF) whose memory-mapped I/O space that must be mitigated.
old-location: pci\sriov_mitigated_range_update_input.htm
tech.root: PCI
ms.assetid: ae4936ac-9794-4854-81ec-2139b3ce4c3c
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PSRIOV_MITIGATED_RANGE_UPDATE_INPUT, PCI.sriov_mitigated_range_update_input, SRIOV_MITIGATED_RANGE_UPDATE_INPUT, SRIOV_MITIGATED_RANGE_UPDATE_INPUT structure [Buses], _SRIOV_MITIGATED_RANGE_UPDATE_INPUT, pcivirt/SRIOV_MITIGATED_RANGE_UPDATE_INPUT"
ms.prod: windows-hardware
ms.technology: windows-devices
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
-	pcivirt.h
api_name:
-	SRIOV_MITIGATED_RANGE_UPDATE_INPUT
product:
- Windows
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGE_UPDATE_INPUT, *PSRIOV_MITIGATED_RANGE_UPDATE_INPUT
---

# _SRIOV_MITIGATED_RANGE_UPDATE_INPUT structure


## -description


This structure is used as an input buffer to the <a href="https://msdn.microsoft.com/f49e6d9e-0b62-4742-9868-1717f8482d9a">IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</a> request to indicate the virtual function (VF) whose memory-mapped I/O space that must be mitigated.


## -syntax


```cpp
typedef struct _SRIOV_MITIGATED_RANGE_UPDATE_INPUT {
  USHORT  VfIndex;
} SRIOV_MITIGATED_RANGE_UPDATE_INPUT, SRIOV_MITIGATED_RANGE_UPDATE_INPUT;
```


## -struct-fields




### -field VfIndex

Zero-based index of the virtual function from the first virtual function exposed by this physical function.

