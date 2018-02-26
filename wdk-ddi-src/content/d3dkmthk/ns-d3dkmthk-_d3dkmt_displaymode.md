---
UID: NS:d3dkmthk._D3DKMT_DISPLAYMODE
title: "_D3DKMT_DISPLAYMODE"
author: windows-driver-content
description: The D3DKMT_DISPLAYMODE structure describes a display mode.
old-location: display\d3dkmt_displaymode.htm
old-project: display
ms.assetid: 04d3d4bd-3926-43bf-b64e-0ba0c2589a54
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: ",  , ,, 3, A, D, D3DKMT_DISPLAYMODE, D3DKMT_DISPLAYMODE structure [Display Devices], E, I, K, L, M, O, OpenGL_Structs_057de1d2-b55b-4ee8-ad2d-28eb01b3168c.xml, P, S, T, Y, _, _D3DKMT_DISPLAYMODE, d3dkmthk/D3DKMT_DISPLAYMODE, display.d3dkmt_displaymode"
ms.prod: windows-hardware
ms.technology: windows-devices
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dkmthk.h
apiname:
-	D3DKMT_DISPLAYMODE
product: Windows
targetos: Windows
req.typenames: D3DKMT_DISPLAYMODE
---

# _D3DKMT_DISPLAYMODE structure


## -description


The D3DKMT_DISPLAYMODE structure describes a display mode.


## -syntax


````
typedef struct _D3DKMT_DISPLAYMODE {
  UINT                                  Width;
  UINT                                  Height;
  D3DDDIFORMAT                          Format;
  UINT                                  IntegerRefreshRate;
  D3DDDI_RATIONAL                       RefreshRate;
  D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING ScanLineOrdering;
  D3DDDI_ROTATION                       DisplayOrientation;
  UINT                                  DisplayFixedOutput;
  D3DKMDT_DISPLAYMODE_FLAGS             Flags;
} D3DKMT_DISPLAYMODE;
````


## -struct-fields




### -field Width

[out] The screen width of the display mode, in pixels.


### -field Height

[out] The screen height of the display mode, in pixels.


### -field Format

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>-typed value that indicates the pixel format of the display mode.


### -field IntegerRefreshRate

[out] A UINT value that indicates the refresh rate of the display mode. 


### -field RefreshRate

[out] A <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a> structure that indicates the refresh rate of the display mode. 


### -field ScanLineOrdering

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_video_signal_scanline_ordering.md">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>-typed value that indicates how scan lines are ordered in the display mode.


### -field DisplayOrientation

[out] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>-typed value that identifies the orientation of the display mode.


### -field DisplayFixedOutput

[out] The fixed output of the display mode.


### -field Flags

[out] A <a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmdt_displaymode_flags.md">D3DKMDT_DISPLAYMODE_FLAGS</a> structure that indicates information about the display mode.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_rational.md">D3DDDI_RATIONAL</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddiformat.md">D3DDDIFORMAT</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_rotation.md">D3DDDI_ROTATION</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmt_getdisplaymodelist.md">D3DKMT_GETDISPLAYMODELIST</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtgetdisplaymodelist.md">D3DKMTGetDisplayModeList</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_video_signal_scanline_ordering.md">D3DDDI_VIDEO_SIGNAL_SCANLINE_ORDERING</a>



<a href="..\d3dkmthk\ns-d3dkmthk-_d3dkmdt_displaymode_flags.md">D3DKMDT_DISPLAYMODE_FLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_DISPLAYMODE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

