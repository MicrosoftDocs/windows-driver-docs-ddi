---
UID: NC:d3d12umddi.PFND3D12DDI_SETVIEWINSTANCEMASK_0033
title: PFND3D12DDI_SETVIEWINSTANCEMASK_0033 (d3d12umddi.h)
description: Used to set a view instance mask.
old-location: display\pfnd3d12ddi_setviewinstancemask_0033.htm
ms.assetid: 0A41AC01-9F45-4026-9451-AEF2732C9084
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback function"]
ms.keywords: PFND3D12DDI_SETVIEWINSTANCEMASK_0033, PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback, PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback function [Display Devices], d3d12umddi/PFND3D12DDI_SETVIEWINSTANCEMASK_0033, display.pfnd3d12ddi_setviewinstancemask_0033
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_SETVIEWINSTANCEMASK_0033"
 - "PFND3D12DDI_SETVIEWINSTANCEMASK_0033"
req.header: d3d12umddi.h
req.include-header:
req.target-type: Windows
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- d3d12umddi.h
api_name:
- PFND3D12DDI_SETVIEWINSTANCEMASK_0033
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_SETVIEWINSTANCEMASK_0033 callback function


## -description


Used to set a view instance mask.


## -parameters




### -param Arg1

*hCommandList*

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Mask

The mask that will be set.




