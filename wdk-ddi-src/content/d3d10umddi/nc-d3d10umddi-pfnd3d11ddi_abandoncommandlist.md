---
UID: NC:d3d10umddi.PFND3D11DDI_ABANDONCOMMANDLIST
title: PFND3D11DDI_ABANDONCOMMANDLIST (d3d10umddi.h)
description: The AbandonCommandList function abandons the command list.
old-location: display\abandoncommandlist.htm
ms.date: 05/10/2018
keywords: ["PFND3D11DDI_ABANDONCOMMANDLIST callback function"]
ms.keywords: AbandonCommandList, AbandonCommandList callback function [Display Devices], PFND3D11DDI_ABANDONCOMMANDLIST, PFND3D11DDI_ABANDONCOMMANDLIST callback, UserModeDisplayDriverDx11_Functions_1f9b5b27-499e-41a0-adf3-7b1c2f0021c7.xml, d3d10umddi/AbandonCommandList, display.abandoncommandlist
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Desktop
req.target-min-winverclnt: AbandonCommandList is supported beginning with the Windows 7 operating system.
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
 - PFND3D11DDI_ABANDONCOMMANDLIST
 - d3d10umddi/PFND3D11DDI_ABANDONCOMMANDLIST
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3d10umddi.h
api_name:
 - PFND3D11DDI_ABANDONCOMMANDLIST
---

# PFND3D11DDI_ABANDONCOMMANDLIST callback function


## -description

The <b>AbandonCommandList</b> function abandons the command list.

## -parameters

### -param unnamedParam1

*hDevice* [in]

A handle to the display device (graphics context).

## -remarks

The driver can use the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_seterror_cb">pfnSetErrorCb</a> callback function to set a critical error code. 







After a deferred context is abandoned, the Direct3D runtime calls <b>AbandonCommandList</b> to abandon the command list that is associated with the deferred context. <b>AbandonCommandList</b> can apply state into whatever the driver prefers. 

The driver is only required to implement <b>AbandonCommandList</b> if the driver supports the D3D11DDICAPS_COMMANDLISTS_BUILD_2 capability that can be returned in the <a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a> structure from a call to the <a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a> function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_devicefuncs">D3D11DDI_DEVICEFUNCS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/ns-d3d10umddi-d3d11ddi_threading_caps">D3D11DDI_THREADING_CAPS</a>



<a href="/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10_2ddi_getcaps">GetCaps(D3D10_2)</a>

