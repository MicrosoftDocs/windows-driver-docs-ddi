---
UID: NS:d3d12umddi.D3D12DDIARG_CREATECOMMANDQUEUE_0050
title: D3D12DDIARG_CREATECOMMANDQUEUE_0050
author: windows-driver-content
description: Arguments used to create a hardware command queue.
ms.assetid: ff28c67f-17f9-417c-bdb3-bdaf00056b37
ms.date: 10/19/2018
ms.topic: struct
ms.keywords: D3D12DDIARG_CREATECOMMANDQUEUE_0050, D3D12DDIARG_CREATECOMMANDQUEUE_0050, 
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
req.typenames: D3D12DDIARG_CREATECOMMANDQUEUE_0050
topic_type: 
-	apiref
api_type: 
-	HeaderDef
api_location: 
-	d3d12umddi.h
api_name: 
-	D3D12DDIARG_CREATECOMMANDQUEUE_0050
product:
-	Windows
targetos: Windows
tech.root: display
---

# D3D12DDIARG_CREATECOMMANDQUEUE_0050 structure

## -description

Arguments used to create a hardware command queue.

## -struct-fields

### -field QueueFlags

Command queue flags.

### -field NodeMask

The node mask of the command list.

### -field QueueCreationFlags

Command queue creation flags.

### -field SchedulingGroup
 
The hardware scheduling group.

## -remarks

The driver is allowed to have a command queue which owns both software-scheduled contexts, and hardware queues, if and only if the command queue also owns the contexts for those hardware queues. Each command queue must be capable of performing broadcast synchronization across only contexts for mixed hardware and software, or only hardware queues.

## -see-also
