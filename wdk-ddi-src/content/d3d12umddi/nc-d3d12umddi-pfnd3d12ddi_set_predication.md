---
UID: NC:d3d12umddi.PFND3D12DDI_SET_PREDICATION
title: PFND3D12DDI_SET_PREDICATION (d3d12umddi.h)
description: The pfnSetPredication callback function denotes that subsequent video operations and resource manipulation commands are not actually performed if the resulting predicate data of the predicate is equal to the operation specified.
old-location: display\pfnd3d12ddi_set_predication.htm
ms.assetid: C5830688-4FC6-4D3F-82EB-15354B28C5F1
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_SET_PREDICATION, PFND3D12DDI_SET_PREDICATION callback, d3d12umddi/pfnSetPredication, display.pfnd3d12ddi_set_predication, pfnSetPredication, pfnSetPredication callback function [Display Devices]
ms.topic: callback
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
req.irql:
topic_type:
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- D3d12umddi.h
api_name:
- pfnSetPredication
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_SET_PREDICATION callback function


## -description


The <i>pfnSetPredication</i> callback function denotes that subsequent video operations and resource manipulation commands are not actually performed if the resulting predicate data of the predicate is equal to the operation specified.


## -parameters




### -param Arg1

*hCommandList*

A handle to the driver's data for the command list. The driver uses this region of memory to store internal data structures that are related to its command list.

### -param Arg2

*hResource*

The handle of a resource.

### -param Arg3


### -param Arg4

*PredicationOp*

A predication operation. For more information, see the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/ne-d3d12umddi-d3d12ddi_predication_op">D3D12DDI_PREDICATION_OP</a> enumeration.



## -returns



This callback function does not return a value.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d12umddi/ne-d3d12umddi-d3d12ddi_predication_op">D3D12DDI_PREDICATION_OP</a>
 

 

