---
UID: NC:d3dhal.LPD3DHAL_CONTEXTCREATECB
title: LPD3DHAL_CONTEXTCREATECB (d3dhal.h)
description: The D3dContextCreate function creates a context.
old-location: display\d3dcontextcreate.htm
tech.root: display
ms.assetid: c960c3f4-7565-4163-b8c2-a13643110c8c
ms.date: 05/10/2018
keywords: ["LPD3DHAL_CONTEXTCREATECB callback function"]
ms.keywords: D3dContextCreate, D3dContextCreate callback function [Display Devices], LPD3DHAL_CONTEXTCREATECB, LPD3DHAL_CONTEXTCREATECB callback, d3dfncs_d126e9ed-3783-4cc1-8fd6-34592b95bec7.xml, d3dhal/D3dContextCreate, display.d3dcontextcreate
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Desktop
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
req.typenames: 
f1_keywords:
 - LPD3DHAL_CONTEXTCREATECB
 - d3dhal/LPD3DHAL_CONTEXTCREATECB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dhal.h
api_name:
 - D3dContextCreate
---

# LPD3DHAL_CONTEXTCREATECB callback function


## -description

The <b>D3dContextCreate</b> function creates a context.

## -parameters

### -param Arg1

*pccd* [in]

Points to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_contextcreatedata">D3DHAL_CONTEXTCREATEDATA</a> structure that contains the information required to create a context and the data that the driver should store in the new context.

## -returns

<b>D3dContextCreate</b> returns one of the following callback codes:

## -remarks

<b>D3dContextCreate</b> must be implemented in drivers that support Microsoft Direct3D. It should perform the following steps:

<ul>
<li>
Initialize the driver's context with all information required by the driver to perform rendering. This includes associating the rendering target and depth buffer that the <b>lpDDSLcl</b> and <b>lpDDSZLcl</b> members of the D3DHAL_CONTEXTCREATEDATA structure at <b>pccd</b> point to, respectively, with the context.

</li>
<li>
Generate a unique context ID for this new context and return it in the <b>dwhContext</b> member of D3DHAL_CONTEXTCREATEDATA. Direct3D uses this context ID in every subsequent callback it makes to this Direct3D device. The driver must never create a context handle of zero.

</li>
<li>
Set the <b>ddrval</b> member of D3DHAL_CONTEXTCREATEDATA to DD_OK upon success, and to D3DHAL_OUTOFCONTEXTS if it cannot create the context.

</li>
<li>
Return DDHAL_DRIVER_HANDLED.

</li>
</ul>
<b>D3dContextCreate</b> should not cache the pointer to the <a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_directdraw_local">DD_DIRECTDRAW_LOCAL</a> structure that was passed in as the <b>lpDDLcl</b> member of D3DHAL_CONTEXTCREATEDATA. If the driver subsequently requires any information that is accessed through this DD_DIRECTDRAW_LOCAL pointer, the driver should store the information in the driver's private context data structure.

State is not shared between contexts; therefore, the driver must maintain full state information for each context. This state is changed by any subsequent calls to <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.

The driver must be able to reference all texture handles that are created within a context. The driver can then clean up all driver-specific data related to textures created within this context when a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a> call is made. 

<b>D3dContextCreate</b> can be called with a disabled <a href="https://docs.microsoft.com/windows-hardware/drivers/">PDEV</a>. A PDEV is disabled or enabled by calling the display driver's <a href="https://docs.microsoft.com/windows/win32/api/winddi/nf-winddi-drvassertmode">DrvAssertMode</a> function. See <a href="https://docs.microsoft.com/windows-hardware/drivers/display/managing-pdevs">Managing PDEVs</a> for more information.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_contextcreatedata">D3DHAL_CONTEXTCREATEDATA</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_contextdestroycb">D3dContextDestroy</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>



<a href="https://docs.microsoft.com/windows/win32/api/ddrawint/ns-ddrawint-dd_directdraw_local">DD_DIRECTDRAW_LOCAL</a>

