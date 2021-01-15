---
UID: NC:d3dkmddi.DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
title: DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES (d3dkmddi.h)
description: The pfnGetNumModes function returns the number of target modes in a specified VidPN target mode set.
old-location: display\dxgk_vidpntargetmodeset_interface_pfngetnummodes.htm
ms.date: 05/10/2018
keywords: ["DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback function"]
ms.keywords: DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES, DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback, VidPnFunctions_f2fa9ea6-6ce7-485d-bcd2-b3c340ca66fc.xml, d3dkmddi/pfnGetNumModes, display.dxgk_vidpntargetmodeset_interface_pfngetnummodes, pfnGetNumModes, pfnGetNumModes callback function [Display Devices]
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
req.irql: PASSIVE_LEVEL
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
 - d3dkmddi/DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dkmddi.h
api_name:
 - DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES
product:
 - Windows
---

# DXGKDDI_VIDPNTARGETMODESET_GETNUMMODES callback function


## -description

The <b>pfnGetNumModes</b> function returns the number of target modes in a specified VidPN target mode set.

## -parameters

### -param hVidPnTargetModeSet

A handle to a VidPN target mode set object. The display miniport driver previously obtained this handle by calling the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpn_acquiretargetmodeset">pfnAcquireTargetModeSet</a> function of the <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_vidpn_interface">DXGK_VIDPN_INTERFACE</a> interface.

### -param pNumTargetModes

A pointer to a SIZE_T-typed variable that receives the number of target modes in the set.

## -returns

The <b>pfnGetNumModes</b> function returns one of the following values:

|Return code|Description|
|--- |--- |
|STATUS_SUCCESS|The function succeeded.|
|STATUS_GRAPHICS_INVALID_VIDPN_TARGETMODESET|The handle supplied in hVidPnTargetModeSet was invalid.|

## -remarks

The D3DKMDT_HVIDPNTARGETMODESET data type is defined in <i>D3dkmdt.h</i>.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirefirstmodeinfo">pfnAcquireFirstModeInfo</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_vidpntargetmodeset_acquirenextmodeinfo">pfnAcquireNextModeInfo</a>

