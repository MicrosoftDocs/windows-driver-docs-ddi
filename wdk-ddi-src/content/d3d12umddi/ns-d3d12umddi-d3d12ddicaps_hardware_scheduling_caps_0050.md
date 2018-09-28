---
UID: NS:d3d12umddi.D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050
title: D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050
author: windows-driver-content
description: Determines how the runtime will manage associations of 3D and compute queues to scheduling groups.
ms.assetid: 3e74a66b-30bc-4831-bdee-28d5a8aa26fc
ms.author: windowsdriverdev
ms.date: 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050, D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050, 
req.header: d3d12umddi.h
req.include-header:
req.target-type:
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDICAPS_HARDWARE_SCHEDULING_CAPS_0050 structure

## -description

Determines how the runtime will manage associations of 3D and compute queues to scheduling groups.

The runtime will manage associations of 3D and compute queues to scheduling groups, on a first-come-first-serve basis.

## -struct-fields

### -field ComputeQueuesPer3DQueue
 
The number of compute API-level command queues that should be associated with a scheduling group. 


## -remarks

The runtime will only assign one 3D command queue per node per scheduling group. If the driver reports a cap value of 0, the runtime will not attempt to create scheduling groups, and all contexts will continue to be owned by command queues directly.

Otherwise, the runtime will maintain a device-local set of scheduling groups. Every time a 3D/compute command queue is created, the runtime will runtime the following logic:

1. If an existing scheduling group has a slot for the particular type of command queue being created, fill that slot. Existing scheduling groups are searched in the order they were created.
2. Otherwise, create a new scheduling group to assign the new command queue to.

## -see-also