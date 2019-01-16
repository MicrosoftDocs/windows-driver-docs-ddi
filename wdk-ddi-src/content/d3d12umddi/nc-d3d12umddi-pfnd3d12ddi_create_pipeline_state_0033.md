---
UID: NC:d3d12umddi.PFND3D12DDI_CREATE_PIPELINE_STATE_0033
title: PFND3D12DDI_CREATE_PIPELINE_STATE_0033
description: Used to create a pipeline state.
old-location: display\pfnd3d12ddi_create_pipeline_state_0033.htm
ms.assetid: F8255544-D5B6-4692-BDC0-EF5A2B856153
ms.date: 05/10/2018
ms.keywords: PFND3D12DDI_CREATE_PIPELINE_STATE_0033, PFND3D12DDI_CREATE_PIPELINE_STATE_0033 entry, PFND3D12DDI_CREATE_PIPELINE_STATE_0033 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CREATE_PIPELINE_STATE_0033, display.pfnd3d12ddi_create_pipeline_state_0033
ms.topic: callback
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
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3d12umddi.h
api_name:
-	PFND3D12DDI_CREATE_PIPELINE_STATE_0033
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# PFND3D12DDI_CREATE_PIPELINE_STATE_0033 callback function


## -description


Used to create a pipeline state.


## -parameters




### -param Arg1

A handle to the display device (graphics context).

### -param *

The arguments used to create a pipeline state.

### -param Arg2

The handle of the pipeline state.

### -param Arg3

The handle of the pipeline state for the driver to use when it calls back into the runtime.



## -returns



Returns STATUS_SUCCESS if completed successfully.



