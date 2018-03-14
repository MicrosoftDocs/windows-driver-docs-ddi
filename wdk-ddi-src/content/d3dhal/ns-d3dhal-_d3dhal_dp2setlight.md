---
UID: NS:d3dhal._D3DHAL_DP2SETLIGHT
title: "_D3DHAL_DP2SETLIGHT"
author: windows-driver-content
description: The D3DHAL_DP2SETLIGHT structure allows lights to be set for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setlight.htm
old-project: display
ms.assetid: 442b5867-b420-46eb-a751-cd460641c505
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: "*LPD3DHAL_DP2SETLIGHT, D3DHAL_DP2SETLIGHT, D3DHAL_DP2SETLIGHT structure [Display Devices], LPD3DHAL_DP2SETLIGHT, LPD3DHAL_DP2SETLIGHT structure pointer [Display Devices], _D3DHAL_DP2SETLIGHT, d3dhal/D3DHAL_DP2SETLIGHT, d3dhal/LPD3DHAL_DP2SETLIGHT, d3dstrct_253f0e1b-ff61-4324-a75f-25577bce318b.xml, display.d3dhal_dp2setlight"
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
-	D3DHAL_DP2SETLIGHT
product: Windows
targetos: Windows
req.typenames: D3DHAL_DP2SETLIGHT
---

# _D3DHAL_DP2SETLIGHT structure


## -description


The D3DHAL_DP2SETLIGHT structure allows lights to be set for <a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>.


## -syntax


````
typedef struct _D3DHAL_DP2SETLIGHT {
  DWORD dwIndex;
  DWORD dwDataType;
} D3DHAL_DP2SETLIGHT, *LPD3DHAL_DP2SETLIGHT;
````


## -struct-fields




### -field dwIndex

Specifies an index into an array of lights.


### -field dwDataType

Specifies the type of data being passed.

<table>
<tr>
<th>Value</th>
<th>Meaning</th>
</tr>
<tr>
<td>
D3DHAL_SETLIGHT_DATA

</td>
<td>
Specifies that a D3DLIGHT7 (described in the Microsoft Windows SDK documentation) structure defining the light follows immediately in the command stream.

</td>
</tr>
<tr>
<td>
D3DHAL_SETLIGHT_ENABLE

</td>
<td>
Enables the light whose index is specified in <b>dwIndex</b>.

</td>
</tr>
<tr>
<td>
D3DHAL_SETLIGHT_DISABLE

</td>
<td>
Disables the light whose index is specified in <b>dwIndex</b>.

</td>
</tr>
</table>
 


## -see-also

<a href="..\d3dhal\nc-d3dhal-lpd3dhal_drawprimitives2cb.md">D3dDrawPrimitives2</a>



 

 


