---
UID: NC:d3d12umddi.PFND3D12DDI_OPENADAPTER
title: PFND3D12DDI_OPENADAPTER (d3d12umddi.h)
description: The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls.
old-location: display\pfnd3d12ddi_openadapter.htm
ms.assetid: FEDC2FB5-9F1A-4829-A98D-3BEA4218AE3D
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_OPENADAPTER callback function"]
ms.keywords: PFND3D12DDI_OPENADAPTER, PFND3D12DDI_OPENADAPTER callback, PFND3D12DDI_OPENADAPTER callback function [Display Devices], d3d12umddi/PFND3D12DDI_OPENADAPTER, display.pfnd3d12ddi_openadapter
req.header: d3d12umddi.h
req.include-header: 
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_OPENADAPTER
 - d3d12umddi/PFND3D12DDI_OPENADAPTER
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d12umddi.h
api_name:
 - PFND3D12DDI_OPENADAPTER
product:
 - Windows
---

# PFND3D12DDI_OPENADAPTER callback function


## -description

The PFND3D12DDI_OPENADAPTER function creates a graphics adapter object that is referenced in subsequent calls.

## -parameters

### -param Arg1

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddiarg_openadapter">D3D12DDIARG_OPENADAPTER</a> structure. On input, this structure contains information that the driver can use. On output, the driver specifies information that the Microsoft Direct3D runtime can use.

## -returns

PFND3D12DDI_OPENADAPTER returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The graphics adapter object was successfully created.|
|E_OUTOFMEMORY|PFND3D12DDI_OPENADAPTER could not allocate memory that was required for it to complete.|

## -remarks

The graphics adapter object that is created by the PFND3D12DDI_OPENADAPTER function represents the underlying graphics hardware. Before the Direct3D runtime can create a display device by calling <a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_createdevice_0003">PFND3D12DDI_CREATEDEVICE_0003</a>, the user-mode display driver should call the <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_queryadapterinfocb">pfnQueryAdapterInfoCb</a> function to query for the graphics hardware capabilities from the display miniport driver. 

The Direct3D runtime can open multiple graphics adapter objects from a single graphics adapter.