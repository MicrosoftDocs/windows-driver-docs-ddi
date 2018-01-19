---
UID: NS:dxva._DXVA_DeinterlaceCaps
title: _DXVA_DeinterlaceCaps
author: windows-driver-content
description: The DXVA_DeinterlaceCaps structure describes the driver capabilities for a deinterlace mode.
old-location: display\dxva_deinterlacecaps.htm
old-project: display
ms.assetid: be503505-fb20-4a8d-b395-7e807cde9fb6
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: _DXVA_DeinterlaceCaps, DXVA_DeinterlaceCaps, *LPDXVA_DeinterlaceCaps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: dxva.h
req.include-header: Dxva.h
req.target-type: Windows
req.target-min-winverclnt: 
req.target-min-winversvr: 
req.kmdf-ver: 
req.umdf-ver: 
req.alt-api: DXVA_DeinterlaceCaps
req.alt-loc: dxva.h
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
req.typenames: DXVA_DeinterlaceCaps, *LPDXVA_DeinterlaceCaps
---

# _DXVA_DeinterlaceCaps structure



## -description
The DXVA_DeinterlaceCaps structure describes the driver capabilities for a deinterlace mode.



## -syntax

````
typedef struct _DXVA_DeinterlaceCaps {
  DWORD                 Size;
  DWORD                 NumPreviousOutputFrames;
  DWORD                 InputPool;
  DWORD                 NumForwardRefSamples;
  DWORD                 NumBackwardRefSamples;
  D3DFORMAT             d3dOutputFormat;
  DXVA_VideoProcessCaps VideoProcessingCaps;
  DXVA_DeinterlaceTech  DeinterlaceTechnology;
} DXVA_DeinterlaceCaps, *LPDXVA_DeinterlaceCaps;
````


## -struct-fields

### -field Size

Indicates the size of this structure.


### -field NumPreviousOutputFrames

Indicates the number of required frames previously output by the deinterlace algorithm. This member is used by recursive deinterlace algorithms.


### -field InputPool

Indicates the memory pool from which the interlaced source surfaces should be allocated. For more information, see the D3DPOOL enumeration type in the Microsoft Window SDK documentation. 


### -field NumForwardRefSamples

Indicates the required number of forward reference samples for the defined deinterlace mode. These samples will be in future fields. This value is zero for bob and line blending, and can be several values for adaptive deinterlacing and frame-rate conversion.


### -field NumBackwardRefSamples

Indicates the required backward reference samples for the defined deinterlace mode. The samples are in past fields. This value is zero for bob, 1 for line blending, and can be several values for adaptive deinterlacing and frame-rate conversion.


### -field d3dOutputFormat

Indicates the Direct3D surface format of the output frames. Usually a deinterlace algorithm outputs frames in a surface format that matches the input sample format. This member ensures that the VMR or other video renderer will be able to supply the correct output frame surfaces to the deinterlace hardware.

Note that if the <b>DXVA_Deinterlace_YUV2RGB</b> enumerator is returned in the <a href="..\dxva\ne-dxva-_dxva_videoprocesscaps.md">DXVA_VideoProcessCaps</a> enumeration, the VMR will assume that valid output formats are specified by this member, in addition to a D3DFMT_X8R8G8B8 format.


### -field VideoProcessingCaps

Specifies a <a href="..\dxva\ne-dxva-_dxva_videoprocesscaps.md">DXVA_VideoProcessCaps</a> enumeration indicating the operation that can be performed concurrently with the requested deinterlace. 


### -field DeinterlaceTechnology

Specifies a <a href="..\dxva\ne-dxva-_dxva_deinterlacetech.md">DXVA_DeinterlaceTech</a> enumeration indicating the deinterlacing technology used by this deinterlacing device.


## -remarks
The driver receives the DXVA_DeinterlaceCaps structure with the <b>Size</b> member assigned, assigns values to the remaining members, and returns DXVA_DeinterlaceCaps to the renderer.


## -see-also
<dl>
<dt>
<a href="..\dxva\ne-dxva-_dxva_videoprocesscaps.md">DXVA_VideoProcessCaps</a>
</dt>
<dt>
<a href="..\dxva\ne-dxva-_dxva_deinterlacetech.md">DXVA_DeinterlaceTech</a>
</dt>
</dl>
 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXVA_DeinterlaceCaps structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

