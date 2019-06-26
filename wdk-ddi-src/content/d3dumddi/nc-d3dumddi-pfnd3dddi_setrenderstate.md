---
UID: NC:d3dumddi.PFND3DDDI_SETRENDERSTATE
title: PFND3DDDI_SETRENDERSTATE (d3dumddi.h)
description: The SetRenderState function updates a render state.
old-location: display\setrenderstate.htm
tech.root: display
ms.assetid: 22fb67f7-cc28-4f10-950d-1379769ddf89
ms.date: 05/10/2018
ms.keywords: PFND3DDDI_SETRENDERSTATE, PFND3DDDI_SETRENDERSTATE callback, SetRenderState, SetRenderState callback function [Display Devices], UserModeDisplayDriver_Functions_738b0898-2699-4f3d-8dc1-b4ea4cdbfeae.xml, d3dumddi/SetRenderState, display.setrenderstate
ms.topic: callback
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
- d3dumddi.h
api_name:
- SetRenderState
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_SETRENDERSTATE callback function


## -description


The <i>SetRenderState</i> function updates a render state.


## -parameters




### -param hDevice [in]

A handle to the display device (graphics context).


### -param *








*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_renderstate">D3DDDIARG_RENDERSTATE</a> structure that describes how to update the render state.


## -returns



<i>SetRenderState</i> returns S_OK or an appropriate error result if the render state is not successfully updated.




## -remarks



The Microsoft Direct3D runtime maps <b>BeginScene</b> and <b>EndScene</b> calls from applications to the user-mode display driver's <i>SetRenderState</i> function. When the runtime receives a <b>BeginScene</b> call, it sets the <b>State</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_renderstate">D3DDDIARG_RENDERSTATE</a> structure that is pointed to by <i>pData</i> to D3DRENDERSTATE_SCENECAPTURE and the <b>Value</b> member of D3DDDIARG_RENDERSTATE to <b>TRUE</b> and then calls <i>SetRenderState</i>. When the runtime receives an <b>EndScene</b> call, it sets the <b>State</b> member to D3DRENDERSTATE_SCENECAPTURE and the <b>Value</b> member to <b>FALSE</b> and then calls <i>SetRenderState</i>. In between these calls to <i>SetRenderState</i>, the driver captures geometric data within a frame.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddiarg_renderstate">D3DDDIARG_RENDERSTATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/ns-d3dumddi-_d3dddi_devicefuncs">D3DDDI_DEVICEFUNCS</a>
 

 

