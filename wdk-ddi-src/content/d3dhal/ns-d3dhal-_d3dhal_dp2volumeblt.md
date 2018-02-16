---
UID: NS:d3dhal._D3DHAL_DP2VOLUMEBLT
title: "_D3DHAL_DP2VOLUMEBLT"
author: windows-driver-content
description: DirectX 8.0 and later versions only. The D3DHAL_DP2VOLUMEBLT structure is used for volume texture blts when D3dDrawPrimitives2 responds to the D3DDP2OP_VOLUMEBLT command token.
old-location: display\d3dhal_dp2volumeblt.htm
old-project: display
ms.assetid: 6c301643-1e1b-4b0c-8827-8eae988b1e9b
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dhal/D3DHAL_DP2VOLUMEBLT, D3DHAL_DP2VOLUMEBLT, LPD3DHAL_DP2VOLUMEBLT, _D3DHAL_DP2VOLUMEBLT, D3DHAL_DP2VOLUMEBLT structure [Display Devices], LPD3DHAL_DP2VOLUMEBLT structure pointer [Display Devices], *LPD3DHAL_DP2VOLUMEBLT, d3dhal/LPD3DHAL_DP2VOLUMEBLT, d3dstrct_44b31cb6-2a36-4d2d-91a3-c59b07d8815b.xml, display.d3dhal_dp2volumeblt
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3dhal.h
req.include-header: D3dhal.h
req.target-type: Windows
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
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	d3dhal.h
apiname:
-	D3DHAL_DP2VOLUMEBLT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2VOLUMEBLT
---

# _D3DHAL_DP2VOLUMEBLT structure


## -description



   DirectX 8.0 and later versions only.
   

The D3DHAL_DP2VOLUMEBLT structure is used for volume texture blts when <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> responds to the D3DDP2OP_VOLUMEBLT command token.


## -syntax


````
typedef struct _D3DHAL_DP2VOLUMEBLT {
  DWORD  dwDDDestSurface;
  DWORD  dwDDSrcSurface;
  DWORD  dwDestX;
  DWORD  dwDestY;
  DWORD  dwDestZ;
  D3DBOX srcBox;
  DWORD  dwFlags;
} D3DHAL_DP2VOLUMEBLT, *LPD3DHAL_DP2VOLUMEBLT;
````


## -struct-fields




### -field dwDDDestSurface

Specifies the handle to the destination volume texture.


### -field dwDDSrcSurface

Specifies the handle to the source volume texture.


### -field dwDestX

Specify the location in the destination volume texture to copy the defined source subvolume. These members (<b>dwDestX</b>, <b>dwDestY</b>, and <b>dwDestZ</b>) are specified in screen coordinates.


### -field dwDestY

See <b>dwDestX</b> above.


### -field dwDestZ

See <b>dwDestX</b> above.


### -field srcBox

Specifies a subvolume of the source volume texture to copy to the destination.


### -field dwFlags

Reserved for system use.


## -remarks



The <a href="https://msdn.microsoft.com/dd07e49c-ec1f-4ba6-8b17-80ce6d3c5813">D3dCreateSurfaceEx</a> callback creates the small integer handles to the volume textures that can be used as source and destination volume textures for volume texture blts.

See Remarks for <a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2texblt.md">D3DHAL_DP2TEXBLT</a>.




## -see-also

<a href="https://msdn.microsoft.com/dd07e49c-ec1f-4ba6-8b17-80ce6d3c5813">D3dCreateSurfaceEx</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2texblt.md">D3DHAL_DP2TEXBLT</a>



D3DDP2OP_VOLUMEBLT



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2VOLUMEBLT structure%20 RELEASE:%20(12/29/2017)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

