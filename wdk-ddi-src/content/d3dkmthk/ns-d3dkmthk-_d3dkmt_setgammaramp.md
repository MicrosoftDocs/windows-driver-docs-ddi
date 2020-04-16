---
UID: NS:d3dkmthk._D3DKMT_SETGAMMARAMP
title: _D3DKMT_SETGAMMARAMP (d3dkmthk.h)
description: The D3DKMT_SETGAMMARAMP structure describes parameters for setting the gamma ramp.
old-location: display\d3dkmt_setgammaramp.htm
ms.assetid: aeab6bf1-bb6f-427e-a566-942b3fb061b2
ms.date: 05/10/2018
keywords: ["_D3DKMT_SETGAMMARAMP structure"]
ms.keywords: D3DKMT_SETGAMMARAMP, D3DKMT_SETGAMMARAMP structure [Display Devices], OpenGL_Structs_3f9b4d19-5367-43bb-94a7-288d375412d7.xml, _D3DKMT_SETGAMMARAMP, d3dkmthk/D3DKMT_SETGAMMARAMP, display.d3dkmt_setgammaramp
f1_keywords:
 - "d3dkmthk/D3DKMT_SETGAMMARAMP"
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
req.target-type: Windows
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
- HeaderDef
api_location:
- d3dkmthk.h
api_name:
- D3DKMT_SETGAMMARAMP
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_SETGAMMARAMP
---

# _D3DKMT_SETGAMMARAMP structure


## -description


The D3DKMT_SETGAMMARAMP structure describes parameters for setting the gamma ramp.


## -struct-fields




### -field hDevice

[in] A handle to the device.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the VidPN source. 


### -field Type

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_gammaramp_type">D3DDDI_GAMMARAMP_TYPE</a>-typed value. This member can be one of the following: D3DDDI_GAMMARAMP_UNINITIALIZED (0), D3DDDI_GAMMARAMP_DEFAULT (1), D3DDDI_GAMMARAMP_RGB256x3x16 (2), or D3DDDI_GAMMARAMP_DXGI_1 (3).


### -field pGammaRampRgb256x3x16

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> structure. The union that is contained in D3DKMT_SETGAMMARAMP holds a structure of this type if the <b>Type</b> member is D3DDDI_GAMMARAMP_RGB256x3x16.


### -field pGammaRampDXGI1

[in] A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1">D3DDDI_GAMMA_RAMP_DXGI_1</a> structure. The union that is contained in D3DKMT_SETGAMMARAMP holds a structure of this type if the <b>Type</b> member is D3DDDI_GAMMARAMP_DXGI_1.


### -field Size

[in] The size of the D3DDDI_GAMMA_RAMP_RGB256x3x16 or D3DDDI_GAMMA_RAMP_DXGI_1 structure that <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> or <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1">D3DDDI_GAMMA_RAMP_DXGI_1</a> points to.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ne-d3dukmdt-_d3dddi_gammaramp_type">D3DDDI_GAMMARAMP_TYPE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1">D3DDDI_GAMMA_RAMP_DXGI_1</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16">D3DDDI_GAMMA_RAMP_RGB256x3x16</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtsetgammaramp">D3DKMTSetGammaRamp</a>
 

 

