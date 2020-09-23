---
UID: NC:d3d10umddi.PFND3D11DDI_RECYCLECREATECOMMANDLIST
title: PFND3D11DDI_RECYCLECREATECOMMANDLIST (d3d10umddi.h)
description: The RecycleCreateCommandList function creates a command list and makes a previously unused DDI handle completely valid again.
old-location: display\recyclecreatecommandlist.htm
ms.assetid: c387545e-2891-401d-b7ca-ee7549a52603
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_RECYCLECREATECOMMANDLIST callback function"]
ms.keywords: PFND3D11DDI_RECYCLECREATECOMMANDLIST, PFND3D11DDI_RECYCLECREATECOMMANDLIST callback, RecycleCreateCommandList, RecycleCreateCommandList callback function [Display Devices], UserModeDisplayDriverDx11_Functions_ae724488-211a-4590-abcc-f2c8f954531e.xml, d3d10umddi/RecycleCreateCommandList, display.recyclecreatecommandlist
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: RecycleCreateCommandList is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_RECYCLECREATECOMMANDLIST
 - d3d10umddi/PFND3D11DDI_RECYCLECREATECOMMANDLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - RecycleCreateCommandList
product:
 - Windows
---

# PFND3D11DDI_RECYCLECREATECOMMANDLIST callback function


## -description

The <i>RecycleCreateCommandList</i> function creates a command list and makes a previously unused DDI handle completely valid again.

## -parameters

### -param Arg1

*hDevice* [in]

A handle to the display device (graphics context).

### -param Arg2

*pCreateCommandList* [in]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createcommandlist">D3D11DDIARG_CREATECOMMANDLIST</a> structure that describes the parameters that the user-mode display driver uses to create a command list.

### -param Arg3

*hCommandList* [in]

A handle to the driver's private data for the command list.

### -param Arg4

*hRTCommandList* [in]

A handle to the command list that the driver should use, when it calls back into the Direct3D runtime.

## -returns

<i>RecycleCreateCommandList</i> returns one of the following values:

|Return code|Description|
|--- |--- |
|S_OK|The command list is successfully created.|
|E_OUTOFMEMORY|RecycleCreateCommandList could not allocate memory that is required for it to complete.|

## -remarks

The driver is only required to implement <i>RecycleCreateCommandList</i> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability, which can be returned in the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.

For more information about <i>RecycleCreateCommandList</i>, see <a href="/windows-hardware/drivers/display/supporting-command-lists">Optimization for Small Command Lists</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d11ddi_calcprivatecommandlistsize">CalcPrivateCommandListSize</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddiarg_createcommandlist">D3D11DDIARG_CREATECOMMANDLIST</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>