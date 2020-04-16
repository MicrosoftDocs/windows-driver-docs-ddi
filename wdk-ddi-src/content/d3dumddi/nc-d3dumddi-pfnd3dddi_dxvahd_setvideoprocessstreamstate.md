---
UID: NC:d3dumddi.PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE
title: PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE (d3dumddi.h)
description: The SetVideoProcessStreamState function sets the stream state for a video processor.
old-location: display\setvideoprocessstreamstate.htm
tech.root: display
ms.assetid: b48fbe58-056a-4c3b-8e1e-c65515c21ee4
ms.date: 05/10/2018
keywords: ["PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE callback function"]
ms.keywords: PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE, PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE callback, SetVideoProcessStreamState, SetVideoProcessStreamState callback function [Display Devices], UserModeDisplayDriver_Functions_3860b09d-ba06-4b9e-bf6d-65e7b90135fd.xml, d3dumddi/SetVideoProcessStreamState, display.setvideoprocessstreamstate
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: SetVideoProcessStreamState is supported beginning with the Windows 7 operating system.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - "d3dumddi/SetVideoProcessStreamState"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - SetVideoProcessStreamState
product:
 - Windows
---

# PFND3DDDI_DXVAHD_SETVIDEOPROCESSSTREAMSTATE callback function

## -description

The <i>SetVideoProcessStreamState</i> function sets the stream state for a video processor.

## -parameters

### -param Arg1

### -param Arg2

*hDevice* [in]

A handle to the display device (graphics context).


*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a> structure that describes how to change the stream state.

## -returns

The <i>SetVideoProcessStreamState</i> function returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The stream state is successfully set.|
|E_OUTOFMEMORY|SetVideoProcessStreamState could not allocate the required memory for it to complete.|

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddiarg_dxvahd_setvideoprocessstreamstate">D3DDDIARG_DXVAHD_SETVIDEOPROCESSSTREAMSTATE</a>

