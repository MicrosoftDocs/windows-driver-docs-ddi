---
UID: NS:d3dhal._D3DHAL_DP2SETLIGHT
title: _D3DHAL_DP2SETLIGHT (d3dhal.h)
description: The D3DHAL_DP2SETLIGHT structure allows lights to be set for D3dDrawPrimitives2.
old-location: display\d3dhal_dp2setlight.htm
tech.root: display
ms.assetid: 442b5867-b420-46eb-a751-cd460641c505
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2SETLIGHT structure"]
ms.keywords: "*LPD3DHAL_DP2SETLIGHT, D3DHAL_DP2SETLIGHT, D3DHAL_DP2SETLIGHT structure [Display Devices], LPD3DHAL_DP2SETLIGHT, LPD3DHAL_DP2SETLIGHT structure pointer [Display Devices], _D3DHAL_DP2SETLIGHT, d3dhal/D3DHAL_DP2SETLIGHT, d3dhal/LPD3DHAL_DP2SETLIGHT, d3dstrct_253f0e1b-ff61-4324-a75f-25577bce318b.xml, display.d3dhal_dp2setlight"
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
targetos: Windows
req.typenames: D3DHAL_DP2SETLIGHT
f1_keywords:
 - _D3DHAL_DP2SETLIGHT
 - d3dhal/_D3DHAL_DP2SETLIGHT
 - D3DHAL_DP2SETLIGHT
 - d3dhal/D3DHAL_DP2SETLIGHT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2SETLIGHT
---

# _D3DHAL_DP2SETLIGHT structure


## -description

The D3DHAL_DP2SETLIGHT structure allows lights to be set for <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>.

## -struct-fields

### -field dwIndex

Specifies an index into an array of lights.

### -field dwDataType

Specifies the type of data being passed.

|Value|Meaning|
|--- |--- |
|D3DHAL_SETLIGHT_DATA|Specifies that a D3DLIGHT7 (described in the Microsoft Windows SDK documentation) structure defining the light follows immediately in the command stream.|
|D3DHAL_SETLIGHT_ENABLE|Enables the light whose index is specified in **dwIndex**.|
|D3DHAL_SETLIGHT_DISABLE|Disables the light whose index is specified in **dwIndex**.|

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/nc-d3dhal-lpd3dhal_drawprimitives2cb">D3dDrawPrimitives2</a>

