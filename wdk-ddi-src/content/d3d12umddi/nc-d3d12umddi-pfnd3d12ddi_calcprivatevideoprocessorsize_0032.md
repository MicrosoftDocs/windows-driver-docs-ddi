---
UID: NC:d3d12umddi.PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032
title: PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032 (d3d12umddi.h)
description: Used to calculate the size of a video processor.
old-location: display\pfnd3d12ddi_calcprivatevideoprocessorsize_0032.htm
ms.date: 04/16/2018
keywords: ["PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032 callback function"]
ms.keywords: PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032, PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032 entry, PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032 entry point [Display Devices], d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032, display.pfnd3d12ddi_calcprivatevideoprocessorsize_0032
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
 - PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032
 - d3d12umddi/PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032
product:
 - Windows
---

# PFND3D12DDI_CALCPRIVATEVIDEOPROCESSORSIZE_0032 callback function


## -description

This method is used to calculate the driver object size. The D3D runtime allocates memory for storing the drivers CPU object that represents the video processor.

## -parameters

### -param hDrvDevice

The hardware device being processed.

### -param pArgs

The arguments used to create a video processor.

## -returns

Returns the size of the video processor in bytes.

