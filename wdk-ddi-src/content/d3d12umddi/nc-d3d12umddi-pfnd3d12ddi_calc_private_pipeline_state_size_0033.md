---
UID: NC:d3d12umddi.PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033
title: PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033 (d3d12umddi.h)
description: Used to calculate the pipeline state size.
old-location: display\pfnd3d12ddi_calc_private_pipeline_state_size_0033_.htm
ms.assetid: C119B295-CBCF-46B3-BC8D-3C8AC058F6D8
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033, PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033  entry, PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033, display.pfnd3d12ddi_calc_private_pipeline_state_size_0033_
ms.topic: callback
f1_keywords:
 - "d3d12umddi/PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033"
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
- PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CALC_PRIVATE_PIPELINE_STATE_SIZE_0033 callback function


## -description


Used to calculate the pipeline state size.


## -parameters




### -param Arg1

*hDevice*

A handle to the display device (graphics context).


### -param *

*d3d12ddiarg_create_pipeline_state_0033* [in]

Used to create a pipeline state.



## -returns



The size in bytes of the state size.



