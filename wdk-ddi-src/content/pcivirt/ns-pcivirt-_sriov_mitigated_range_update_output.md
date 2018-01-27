---
UID: NS:pcivirt._SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
title: _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
author: windows-driver-content
description: This structures is the output buffer received by the IOCTL_SRIOV_MITIGATED_RANGE_UPDATE request that indicates the virtual function (VF) whose memory-mapped I/O space was mitigated.
old-location: pci\sriov_mitigated_range_update_output.htm
old-project: PCI
ms.assetid: bd72ac9a-2985-4f2d-8b72-4039c9d3f896
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT structure [Buses], pcivirt/SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, *PSRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, PCI.sriov_mitigated_range_update_output
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
topictype: 
-	APIRef
-	kbSyntax
apitype: 
-	HeaderDef
apilocation: 
-	Pcivirt.h
apiname: 
-	SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
product: Windows
targetos: Windows
req.typenames: SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, *PSRIOV_MITIGATED_RANGE_UPDATE_OUTPUT
---

# _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT structure


## -description


This structures is the output buffer received by the <a href="https://msdn.microsoft.com/f49e6d9e-0b62-4742-9868-1717f8482d9a">IOCTL_SRIOV_MITIGATED_RANGE_UPDATE</a> request that indicates the virtual function (VF) whose memory-mapped I/O space
 was mitigated.


## -syntax


````
typedef struct _SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT {
  USHORT  VfIndex;
} SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT, SRIOV_MITIGATED_RANGE_UPDATE_OUTPUT;
````


## -struct-fields




### -field VfIndex

Zero-based index of the virtual function from the first virtual function exposed by this physical function.

