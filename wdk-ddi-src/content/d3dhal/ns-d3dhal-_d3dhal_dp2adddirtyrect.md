---
UID: NS:d3dhal._D3DHAL_DP2ADDDIRTYRECT
title: _D3DHAL_DP2ADDDIRTYRECT (d3dhal.h)
description: DirectX 8.1 and later versions only. D3DHAL_DP2ADDDIRTYRECT is used to specify that a portion of a 2D resource--a 2D texture or cube texture--was dirtied in system memory. Therefore, this 2D texture must be reloaded into video memory before being used.
old-location: display\d3dhal_dp2adddirtyrect.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DHAL_DP2ADDDIRTYRECT structure"]
ms.keywords: "*LPD3DHAL_DP2ADDDIRTYRECT, D3DHAL_DP2ADDDIRTYRECT, D3DHAL_DP2ADDDIRTYRECT structure [Display Devices], LPD3DHAL_DP2ADDDIRTYRECT, LPD3DHAL_DP2ADDDIRTYRECT structure pointer [Display Devices], _D3DHAL_DP2ADDDIRTYRECT, d3dhal/D3DHAL_DP2ADDDIRTYRECT, d3dhal/LPD3DHAL_DP2ADDDIRTYRECT, d3dstrct_64c25041-cbd9-4073-a42a-e9fb304e0d65.xml, display.d3dhal_dp2adddirtyrect"
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
req.typenames: D3DHAL_DP2ADDDIRTYRECT
f1_keywords:
 - _D3DHAL_DP2ADDDIRTYRECT
 - d3dhal/_D3DHAL_DP2ADDDIRTYRECT
 - D3DHAL_DP2ADDDIRTYRECT
 - d3dhal/D3DHAL_DP2ADDDIRTYRECT
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - D3DHAL_DP2ADDDIRTYRECT
---

# _D3DHAL_DP2ADDDIRTYRECT structure


## -description

   DirectX 8.1 and later versions only.
   

D3DHAL_DP2ADDDIRTYRECT is used to specify that a portion of a 2D resource--a 2D texture or cube texture--was dirtied in system memory. Therefore, this 2D texture must be reloaded into video memory before being used.

## -struct-fields

### -field dwSurface

Specifies the handle to the managed 2D resource that contains a dirtied 2D texture.

### -field rDirtyArea

Specifies the 2D texture that was marked as dirtied. This is a <a href="/windows/win32/api/windef/ns-windef-rectl">RECTL</a> structure.

## -remarks

D3DHAL_DP2ADDDIRTYRECT, along with the DP2OP_ADDDIRTYRECT token, is used only for driver managed resources and surfaces. D3DHAL_DP2ADDDIRTYRECT is never sent unless the driver indicates that it manages resources. To indicate that it manages resources, the driver must set the DDCAPS2_CANMANAGERESOURCE bit, in addition to the DDCAPS2_CANMANAGETEXTURE bit, in the <b>dwCaps2</b> member of a DDCORECAPS structure. The driver specifies this <a href="/windows/win32/api/ddrawi/ns-ddrawi-ddcorecaps">DDCORECAPS</a> structure in the <b>ddCaps</b> member of a <a href="/windows/win32/api/ddrawint/ns-ddrawint-dd_halinfo">DD_HALINFO</a> structure when the driver's <a href="/windows/win32/api/winddi/nf-winddi-drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a> function is called to initialize the DirectDraw component of the driver.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_dp2command">D3DHAL_DP2COMMAND</a>



<a href="/windows-hardware/drivers/ddi/d3dhal/ne-d3dhal-_d3dhal_dp2operation">D3DHAL_DP2OPERATION</a>



<a href="/windows/win32/api/ddrawi/ns-ddrawi-ddcorecaps">DDCORECAPS</a>



<a href="/windows/win32/api/ddrawint/ns-ddrawint-dd_halinfo">DD_HALINFO</a>



<a href="/windows/win32/api/winddi/nf-winddi-drvgetdirectdrawinfo">DrvGetDirectDrawInfo</a>
