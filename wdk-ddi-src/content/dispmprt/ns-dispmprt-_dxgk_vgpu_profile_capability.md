---
UID: NS:dispmprt._DXGK_VGPU_PROFILE_CAPABILITY
title: _DXGK_VGPU_PROFILE_CAPABILITY
author: windows-driver-content
description: Contains information about the virtual GPU profile capability.
tech.root: display
ms.assetid: d9c123d2-5f03-46dd-873c-bf3f6781bcc4
ms.author: windowsdriverdev
ms.date: 04/04/2019 
ms.topic: struct
ms.prod: windows-hardware
ms.technology: windows-devices
ms.keywords: _DXGK_VGPU_PROFILE_CAPABILITY, DXGK_VGPU_PROFILE_CAPABILITY, *PDXGK_VGPU_PROFILE_CAPABILITY, 
req.header: dispmprt.h
req.include-header:
req.target-type:
req.target-min-winverclnt:
req.target-min-winversvr:
req.kmdf-ver:
req.umdf-ver:
req.lib:
req.dll:
req.ddi-compliance:
req.unicode-ansi:
req.max-support:
req.typenames: DXGK_VGPU_PROFILE_CAPABILITY, *PDXGK_VGPU_PROFILE_CAPABILITY
topic_type: 
 - apiref
api_type: 
 - HeaderDef
api_location: 
 - dispmprt.h
api_name: 
 - _DXGK_VGPU_PROFILE_CAPABILITY
product: 
 - Windows
targetos: Windows
---

# _DXGK_VGPU_PROFILE_CAPABILITY structure

## -description

Contains information about the virtual GPU profile capability.

## -struct-fields

### -field TotalValue

Total amount in this partition configuration.

### -field AvailableValue

Currently available amount in this partition configuration. This value changes as vGPUs start and stop running

### -field MinPartitionValue

Minimum value for each partition in this partition configuration.

### -field MaxPartitionValue

Maximum value for each partition in this partition configuration.

### -field OptimalPartitionValue

Optimal value for each partition in this partition configuration.

The meaning of the capability values depend on the capability type.
For memory it is the number of bytes. For compute it is the number of gigaflops of 16fp instructions.
For video Encode/Decode it is roughly in blocks of 540p capability. 1 is 540p60, 2 is 720p60, 4 is 1080p60, 4Kp60 is 16, etc.

## -remarks

## -see-also