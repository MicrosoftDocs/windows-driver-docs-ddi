---
UID: NS:d3dhal._D3DDeviceDesc_V2
title: _D3DDeviceDesc_V2 (d3dhal.h)
description: The D3DDEVICEDESC_V2 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo.
old-location: display\d3ddevicedesc_v2.htm
tech.root: display
ms.assetid: d8ef093e-81f9-443c-9d85-d0d1b6c03416
ms.date: 05/10/2018
keywords: ["_D3DDeviceDesc_V2 structure"]
ms.keywords: "*LPD3DDEVICEDESC_V2, D3DDEVICEDESC_V2, D3DDEVICEDESC_V2 structure [Display Devices], _D3DDeviceDesc_V2, d3dhal/, d3dstrct_93cd326d-38b8-4911-87de-a0b4e81f897c.xml, display.d3ddevicedesc_v2"
f1_keywords:
 - "d3dhal/D3DDEVICEDESC_V2"
 - "D3DDEVICEDESC_V2"
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dhal.h
api_name:
- D3DDEVICEDESC_V2
product:
- Windows
targetos: Windows
req.typenames: D3DDEVICEDESC_V2, *LPD3DDEVICEDESC_V2
---

# _D3DDeviceDesc_V2 structure


## -description


<b>The D3DDEVICEDESC_V2 structure is obsolete; only D3DDEVICEDESC_V1 should be used.</b>

The D3DDEVICEDESC_V2 structure contains fields that are already reported in the 
	 <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_d3dextendedcaps">D3DHAL_D3DEXTENDEDCAPS</a> 
	 structure when responding to the GUID_D3DExtendedCaps GUID in <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a>. 
	 


<pre class="syntax" xml:space="preserve"><code>typedef struct _D3DDeviceDesc_V2 {
    DWORD             dwSize;
    DWORD             dwFlags;
    D3DCOLORMODEL     dcmColorModel;
    DWORD             dwDevCaps;
    D3DTRANSFORMCAPS  dtcTransformCaps;
    BOOL              bClipping;
    D3DLIGHTINGCAPS   dlcLightingCaps;
    D3DPRIMCAPS       dpcLineCaps;
    D3DPRIMCAPS       dpcTriCaps;
    DWORD             dwDeviceRenderBitDepth;
    DWORD             dwDeviceZBufferBitDepth;
    DWORD             dwMaxBufferSize;
    DWORD             dwMaxVertexCount;
    DWORD             dwMinTextureWidth;
    DWORD             dwMinTextureHeight;
    DWORD             dwMaxTextureWidth;
    DWORD             dwMaxTextureHeight;
    DWORD             dwMinStippleWidth;
    DWORD             dwMaxStippleWidth;
    DWORD             dwMinStippleHeight;
    DWORD             dwMaxStippleHeight;
} D3DDEVICEDESC_V2, *LPD3DDEVICEDESC_V2;</code></pre>



## -struct-fields

