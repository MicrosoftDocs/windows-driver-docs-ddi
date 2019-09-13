---
UID: NC:d3d10umddi.PFND3D10_2DDI_GETCAPS
title: PFND3D10_2DDI_GETCAPS (d3d10umddi.h)
description: The GetCaps(D3D10_2) function queries for capabilities of the graphics adapter.
old-location: display\getcaps_d3d10_2_.htm
ms.assetid: 83cd5f34-5f12-4ead-ad33-366fc3c6e804
ms.date: 05/10/2018
ms.keywords: GetCaps, GetCaps callback function [Display Devices], PFND3D10_2DDI_GETCAPS, PFND3D10_2DDI_GETCAPS callback, UserModeDisplayDriverDx11_Functions_b0f0ebe4-205d-4eb5-ad35-e91dbcb21a1c.xml, d3d10umddi/GetCaps, display.getcaps_d3d10_2_
ms.topic: callback
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: GetCaps(D3D10_2) is supported beginning with the Windows 7 operating system.
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
 - "d3d10umddi/GetCaps"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - GetCaps
product:
 - Windows
---

# PFND3D10_2DDI_GETCAPS callback function

## -description

The *GetCaps(D3D10_2)* function queries for capabilities of the graphics adapter.

## -parameters

### -param Arg1

*hAdapter* [in]

A handle that identifies the graphics adapter.

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_2ddiarg_getcaps">D3D10_2DDIARG_GETCAPS</a> structure that describes the capabilities to retrieve.

## -returns

*GetCaps(D3D10_2)* returns one of the following values:

|Return code|Description|
|---|---|
|S_OK|The capabilities are successfully retrieved.|
|E_OUTOFMEMORY|GetCaps(D3D10_2) could not allocate memory that is required for it to complete.|

## -remarks

The data that is returned by the <i>GetCaps(D3D10_2)</i> function in the <b>pData</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_2ddiarg_getcaps">D3D10_2DDIARG_GETCAPS</a> structure depends on the type of data that is requested (that is, the data depends on the <b>Type</b> member of D3D10_2DDIARG_GETCAPS and sometimes on the <b>pInfo</b> member).

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_2ddiarg_getcaps">D3D10_2DDIARG_GETCAPS</a>

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3d10umddi/ns-d3d10umddi-d3d10_2ddi_adapterfuncs">D3D10_2DDI_ADAPTERFUNCS</a>

