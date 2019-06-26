---
UID: NS:d3dkmthk._D3DKMT_DISPLAYMODE
title: _D3DKMT_DISPLAYMODE (d3dkmthk.h)
description: The D3DKMT_DISPLAYMODE structure describes a display mode.
old-location: display\d3dkmt_displaymode.htm
ms.assetid: 04d3d4bd-3926-43bf-b64e-0ba0c2589a54
ms.date: 05/10/2018
ms.keywords: D3DKMT_DISPLAYMODE, D3DKMT_DISPLAYMODE structure [Display Devices], OpenGL_Structs_057de1d2-b55b-4ee8-ad2d-28eb01b3168c.xml, _D3DKMT_DISPLAYMODE, d3dkmthk/D3DKMT_DISPLAYMODE, display.d3dkmt_displaymode
ms.topic: struct
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
- D3DKMT_DISPLAYMODE
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_DISPLAYMODE
---

# _D3DKMT_DISPLAYMODE structure


## -description


The D3DKMT_DISPLAYMODE structure describes a display mode.


## -struct-fields




### -field Width

[out] The screen width of the display mode, in pixels.


### -field Height

[out] The screen height of the display mode, in pixels.


### -field Format

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the display mode.


### -field IntegerRefreshRate

[out] A UINT value that indicates the refresh rate of the display mode. 


### -field RefreshRate

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_rational">D3DDDI_RATIONAL</a> structure that indicates the refresh rate of the display mode. 


### -field ScanLineOrdering

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddi_video_signal_scanline_ordering">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field DisplayOrientation

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field DisplayFixedOutput

[out] The fixed output of the display mode.


### -field Flags

[out] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmdt_displaymode_flags">D3DKMDT_DISPLAYMODE_FLAGS</a> structure that indicates information about the display mode.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddiformat">D3DDDIFORMAT</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ns-d3dukmdt-_d3dddi_rational">D3DDDI_RATIONAL</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddi_rotation">D3DDDI_ROTATION</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dukmdt/ne-d3dukmdt-_d3dddi_video_signal_scanline_ordering">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmdt_displaymode_flags">D3DKMDT_DISPLAYMODE_FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtgetdisplaymodelist">D3DKMTGetDisplayModeList</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/ns-d3dkmthk-_d3dkmt_getdisplaymodelist">D3DKMT_GETDISPLAYMODELIST</a>
 

 

