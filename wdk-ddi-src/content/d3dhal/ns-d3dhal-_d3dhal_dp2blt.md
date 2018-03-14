---
UID: NS:d3dhal._D3DHAL_DP2BLT
title: "_D3DHAL_DP2BLT"
author: windows-driver-content
description: DirectX 9.0 and later versions only. D3DHAL_DP2BLT is used for two dimensional surface blts when D3dDrawPrimitives2 responds to the D3DDP2OP_BLT command token.
old-location: display\d3dhal_dp2blt.htm
old-project: display
ms.assetid: 2d0cdc50-a194-4eda-8bba-f6e5c06ff32c
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2BLT, D3DHAL_DP2BLT, D3DHAL_DP2BLT structure [Display Devices], LPD3DHAL_DP2BLT, LPD3DHAL_DP2BLT structure pointer [Display Devices], _D3DHAL_DP2BLT, d3dhal/D3DHAL_DP2BLT, d3dhal/LPD3DHAL_DP2BLT, d3dstrct_cab5e8b8-ec72-4d7d-8aaa-4a1f6da44a9b.xml, display.d3dhal_dp2blt"
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dhal.h
api_name:
-	D3DHAL_DP2BLT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2BLT
---

# _D3DHAL_DP2BLT structure


## -description



   DirectX 9.0 and later versions only.
   

D3DHAL_DP2BLT is used for two dimensional surface blts when <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a> responds to the D3DDP2OP_BLT command token.


## -syntax


````
typedef struct _D3DHAL_DP2BLT {
  DWORD dwSource;
  RECTL rSource;
  DWORD dwSourceMipLevel;
  DWORD dwDest;
  RECTL rDest;
  DWORD dwDestMipLevel;
  DWORD Flags;
} D3DHAL_DP2BLT, *LPD3DHAL_DP2BLT;
````


## -struct-fields




### -field dwSource

Specifies the handle to the source surface.


### -field rSource

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the source surface. These points define the area of the source blit data and its position on the source surface.


### -field dwSourceMipLevel

Specifies the sublevel of a MIP-map texture that is the source of the blt. 


### -field dwDest

Specifies the handle to the destination surface.


### -field rDest

Specifies a RECTL structure that specifies the upper left and lower right points of a rectangle on the destination surface. These points define the area in which the blit should occur and its position on the destination surface.


### -field dwDestMipLevel

Specifies the sublevel of a MIP-map texture that is the destination for the blt.


### -field Flags

Specifies a flag that indicates the type of filtering that the driver must perform. This member is set to zero to indicate that the driver can use its own filtering technique or is set to one of the following flags.

<table>
<tr>
<th>Flag</th>
<th>Meaning</th>
</tr>
<tr>
<td>
DP2BLT_LINEAR

</td>
<td>
Set for linear filtering.

</td>
</tr>
<tr>
<td>
DP2BLT_POINT

</td>
<td>
Set for point filtering.

</td>
</tr>
</table>
 


## -remarks



The <b>dwSource</b> or <b>dwDest</b> member specifies the kernel handle to the top-level surface and the <b>dwSourceMipLevel</b> or <b>dwDestMiplevel</b> member specifies the sublevel for the MIP-map chain where the blt occurs.




## -see-also

D3DDP2OP_BLT



<a href="..\d3dhal\ns-d3dhal-_d3dhal_dp2command.md">D3DHAL_DP2COMMAND</a>



<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20D3DHAL_DP2BLT structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

