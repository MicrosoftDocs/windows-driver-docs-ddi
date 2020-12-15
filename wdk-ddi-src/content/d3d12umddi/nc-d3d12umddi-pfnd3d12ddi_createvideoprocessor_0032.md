---
UID: NC:d3d12umddi.PFND3D12DDI_CREATEVIDEOPROCESSOR_0032
title: PFND3D12DDI_CREATEVIDEOPROCESSOR_0032 (d3d12umddi.h)
description: Used to create a video processor.
old-location: display\pfnd3d12ddi_createvideoprocessor_0032_.htm
ms.date: 04/16/2018
keywords: ["PFND3D12DDI_CREATEVIDEOPROCESSOR_0032 callback function"]
ms.keywords: PFND3D12DDI_CREATEVIDEOPROCESSOR_0032, PFND3D12DDI_CREATEVIDEOPROCESSOR_0032  callback, PFND3D12DDI_CREATEVIDEOPROCESSOR_0032 callback function [Display Devices], d3d12umddi/PFND3D12DDI_CREATEVIDEOPROCESSOR_0032, display.pfnd3d12ddi_createvideoprocessor_0032_
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_CREATEVIDEOPROCESSOR_0032
 - d3d12umddi/PFND3D12DDI_CREATEVIDEOPROCESSOR_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CREATEVIDEOPROCESSOR_0032
product:
 - Windows
---

# PFND3D12DDI_CREATEVIDEOPROCESSOR_0032 callback function


## -description

The <i>pfnCreateVideoProcessor</i> callback function creates a video processor.

## -parameters

### -param hDrvDevice

The hardware device being processed.

### -param pArgs

The arguments used to create a video processor.

### -param hDrvVideoProcessor

The video processor.

## -returns

Returns STATUS_SUCCESS if completed successfully.

