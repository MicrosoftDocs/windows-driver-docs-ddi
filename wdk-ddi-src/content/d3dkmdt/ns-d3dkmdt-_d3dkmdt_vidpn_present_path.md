---
UID: NS:d3dkmdt._D3DKMDT_VIDPN_PRESENT_PATH
title: "_D3DKMDT_VIDPN_PRESENT_PATH"
author: windows-driver-content
description: The D3DKMDT_VIDPN_PRESENT_PATH structure contains information about a video present path.
old-location: display\d3dkmdt_vidpn_present_path.htm
old-project: display
ms.assetid: 3676476d-babe-4d68-995b-b7068a587bbc
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: D3DKMDT_VIDPN_PRESENT_PATH, D3DKMDT_VIDPN_PRESENT_PATH structure [Display Devices], DmStructs_7cf350db-f1fa-492f-96d2-9ad806f2b75a.xml, _D3DKMDT_VIDPN_PRESENT_PATH, d3dkmdt/D3DKMDT_VIDPN_PRESENT_PATH, display.d3dkmdt_vidpn_present_path
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
-	d3dkmdt.h
api_name:
-	D3DKMDT_VIDPN_PRESENT_PATH
product: Windows
targetos: Windows
req.typenames: D3DKMDT_VIDPN_PRESENT_PATH
---

# _D3DKMDT_VIDPN_PRESENT_PATH structure


## -description


The D3DKMDT_VIDPN_PRESENT_PATH structure contains information about a video present path.


## -syntax


````
typedef struct _D3DKMDT_VIDPN_PRESENT_PATH {
  D3DDDI_VIDEO_PRESENT_SOURCE_ID            VidPnSourceId;
  D3DDDI_VIDEO_PRESENT_TARGET_ID            VidPnTargetId;
  D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE     ImportanceOrdinal;
  D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION ContentTransformation;
  D3DKMDT_2DOFFSET                          VisibleFromActiveTLOffset;
  D3DKMDT_2DOFFSET                          VisibleFromActiveBROffset;
  D3DKMDT_COLOR_BASIS                       VidPnTargetColorBasis;
  D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES        VidPnTargetColorCoeffDynamicRanges;
  D3DKMDT_VIDPN_PRESENT_PATH_CONTENT        Content;
  D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION CopyProtection;
  D3DKMDT_GAMMA_RAMP                        GammaRamp;
} D3DKMDT_VIDPN_PRESENT_PATH;
````


## -struct-fields




### -field VidPnSourceId

The identifier of the path's video present source.


### -field VidPnTargetId

The identifier of the path's video present target.


### -field ImportanceOrdinal

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_importance.md">D3DKMDT_VIDPN_PRESENT_PATH_IMPORTANCE</a> enumerator that specifies the importance of the path relative to other paths. For example, the path presenting the primary view might have higher importance than other paths so that it will be assigned the best source and target mode sets. Path importance ordinal numbers are unique within a given video present network (VidPN) topology. 


### -field ContentTransformation

 A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_transformation.md">D3DKMDT_VIDPN_PRESENT_PATH_TRANSFORMATION</a> enumerator that indicates the transformation applied to the content presented on the video present path.


### -field VisibleFromActiveTLOffset

A D3DKMDT_2DOFFSET structure that contains the offset, in pixels, from the top-left corner of the video signal's active pixels to the top-left corner of the monitor's visible pixels. The D3DKMDT_2DOFFSET data type is defined in <i>D3dkmdt.h</i> as a <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_2dregion.md">D3DKMDT_2DREGION</a> structure.


### -field VisibleFromActiveBROffset

A D3DKMDT_2DOFFSET structure that contains the offset, in pixels, from the lower-right corner of the video signal's active pixels to the lower-right corner of the monitor's visible pixels.


### -field VidPnTargetColorBasis

A <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_color_basis.md">D3DKMDT_COLOR_BASIS</a> enumerator that specifies the color basis used by the path's video present target.


### -field VidPnTargetColorCoeffDynamicRanges

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_color_coeff_dynamic_ranges.md">D3DKMDT_COLOR_COEFF_DYNAMIC_RANGES</a> structure that specifies a range for each channel in the color basis used by the path's video present target.


### -field Content

A value from the <a href="..\d3dkmdt\ne-d3dkmdt-_d3dkmdt_vidpn_present_path_content.md">D3DKMDT_VIDPN_PRESENT_PATH_CONTENT</a> enumeration that indicates the type of content, graphics or video, displayed by the path.


### -field CopyProtection

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_vidpn_present_path_copyprotection.md">D3DKMDT_VIDPN_PRESENT_PATH_COPYPROTECTION</a> structure that describes the copy protection supported by, and currently active on, the path.


### -field GammaRamp

A <a href="..\d3dkmdt\ns-d3dkmdt-_d3dkmdt_gamma_ramp.md">D3DKMDT_GAMMA_RAMP</a> structure that contains a description of a gamma lookup table and a pointer to the lookup table.


## -remarks



A video present path represents a connection between a video present source (view) and a video present target (output) on a display adapter. For more information about video present networks, paths, sources, and targets, see <a href="https://msdn.microsoft.com/62a92f00-b1da-41c2-99af-eef8140b064e">Introduction to Video Present Networks</a>.




## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_updateactivevidpnpresentpath.md">DxgkDdiUpdateActiveVidPnPresentPath</a>



 

 


