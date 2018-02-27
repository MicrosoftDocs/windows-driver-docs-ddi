---
UID: NS:d3dkmthk._D3DKMT_SETGAMMARAMP
title: "_D3DKMT_SETGAMMARAMP"
author: windows-driver-content
description: The D3DKMT_SETGAMMARAMP structure describes parameters for setting the gamma ramp.
old-location: display\d3dkmt_setgammaramp.htm
old-project: display
ms.assetid: aeab6bf1-bb6f-427e-a566-942b3fb061b2
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: D3DKMT_SETGAMMARAMP, D3DKMT_SETGAMMARAMP structure [Display Devices], OpenGL_Structs_3f9b4d19-5367-43bb-94a7-288d375412d7.xml, _D3DKMT_SETGAMMARAMP, d3dkmthk/D3DKMT_SETGAMMARAMP, display.d3dkmt_setgammaramp
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmthk.h
api_name:
-	D3DKMT_SETGAMMARAMP
product: Windows
targetos: Windows
req.typenames: D3DKMT_SETGAMMARAMP
---

# _D3DKMT_SETGAMMARAMP structure


## -description


The D3DKMT_SETGAMMARAMP structure describes parameters for setting the gamma ramp.


## -syntax


````
typedef struct _D3DKMT_SETGAMMARAMP {
  D3DKMT_HANDLE                  hDevice;
  D3DDDI_VIDEO_PRESENT_SOURCE_ID VidPnSourceId;
  D3DDDI_GAMMARAMP_TYPE          Type;
  union {
    D3DDDI_GAMMA_RAMP_RGB256x3x16 *pGammaRampRgb256x3x16;
    D3DDDI_GAMMA_RAMP_DXGI_1      *pGammaRampDXGI1;
  };
  UINT                           Size;
} D3DKMT_SETGAMMARAMP;
````


## -struct-fields




### -field hDevice

[in] A handle to the device.


### -field VidPnSourceId

[in] The zero-based identification number of the video present source in a path of a video present network (VidPN) topology for the VidPN source. 


### -field Type

[in] A <a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_gammaramp_type.md">D3DDDI_GAMMARAMP_TYPE</a>-typed value. This member can be one of the following: D3DDDI_GAMMARAMP_UNINITIALIZED (0), D3DDDI_GAMMARAMP_DEFAULT (1), D3DDDI_GAMMARAMP_RGB256x3x16 (2), or D3DDDI_GAMMARAMP_DXGI_1 (3).


### -field Size

[in] The size of the D3DDDI_GAMMA_RAMP_RGB256x3x16 or D3DDDI_GAMMA_RAMP_DXGI_1 structure that <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16.md">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> or <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1.md">D3DDDI_GAMMA_RAMP_DXGI_1</a> points to.


#### - pGammaRampDXGI1

[in] A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1.md">D3DDDI_GAMMA_RAMP_DXGI_1</a> structure. The union that is contained in D3DKMT_SETGAMMARAMP holds a structure of this type if the <b>Type</b> member is D3DDDI_GAMMARAMP_DXGI_1.


#### - pGammaRampRgb256x3x16

[in] A pointer to a <a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16.md">D3DDDI_GAMMA_RAMP_RGB256x3x16</a> structure. The union that is contained in D3DKMT_SETGAMMARAMP holds a structure of this type if the <b>Type</b> member is D3DDDI_GAMMARAMP_RGB256x3x16.


## -see-also

<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_dxgi_1.md">D3DDDI_GAMMA_RAMP_DXGI_1</a>



<a href="..\d3dukmdt\ne-d3dukmdt-_d3dddi_gammaramp_type.md">D3DDDI_GAMMARAMP_TYPE</a>



<a href="..\d3dukmdt\ns-d3dukmdt-_d3dddi_gamma_ramp_rgb256x3x16.md">D3DDDI_GAMMA_RAMP_RGB256x3x16</a>



<a href="..\d3dkmthk\nf-d3dkmthk-d3dkmtsetgammaramp.md">D3DKMTSetGammaRamp</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DKMT_SETGAMMARAMP structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

