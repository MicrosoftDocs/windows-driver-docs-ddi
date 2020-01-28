---
UID: NS:d3dhal._D3DDeviceDesc_V3
title: _D3DDeviceDesc_V3 (d3dhal.h)
description: The D3DDEVICEDESC_V3 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo.
old-location: display\d3ddevicedesc_v3.htm
tech.root: display
ms.assetid: 36a7b29a-f744-42c8-9e60-9b5dbba3a32f
ms.date: 05/10/2018
ms.keywords: "*LPD3DDEVICEDESC_V3, D3DDEVICEDESC_V3, D3DDEVICEDESC_V3 structure [Display Devices], _D3DDeviceDesc_V3, d3dhal/, d3dstrct_ae7c0a55-4597-4272-9b06-bc74a8340842.xml, display.d3ddevicedesc_v3"
f1_keywords:
 - "d3dhal/D3DDEVICEDESC_V3"
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
- D3DDEVICEDESC_V3
product:
- Windows
targetos: Windows
req.typenames: D3DDEVICEDESC_V3, *LPD3DDEVICEDESC_V3
---

# _D3DDeviceDesc_V3 structure


## -description


<b>The D3DDEVICEDESC_V3 structure is obsolete; only D3DDEVICEDESC_V1 should be used.</b>

The D3DDEVICEDESC_V3 structure contains fields that are already reported in the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dhal/ns-d3dhal-_d3dhal_d3dextendedcaps">D3DHAL_D3DEXTENDEDCAPS</a> structure when responding to the GUID_D3DExtendedCaps GUID in <a href="https://docs.microsoft.com/windows/desktop/api/ddrawint/nc-ddrawint-pdd_getdriverinfo">DdGetDriverInfo</a>.


<pre class="syntax" xml:space="preserve"><code>typedef struct _D3DDeviceDesc_V3 {
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
    DWORD             dwMaxTextureRepeat;
    DWORD             dwMaxTextureAspectRatio;
    DWORD             dwMaxAnisotropy;
    D3DVALUE          dvGuardBandLeft;
    D3DVALUE          dvGuardBandTop;
    D3DVALUE          dvGuardBandRight;
    D3DVALUE          dvGuardBandBottom;
    D3DVALUE          dvExtentsAdjust;
    DWORD             dwStencilCaps;
    DWORD             dwFVFCaps; 
    DWORD             dwTextureOpCaps;
    WORD              wMaxTextureBlendStages;
    WORD              wMaxSimultaneousTextures;
} D3DDEVICEDESC_V3, *LPD3DDEVICEDESC_V3;
</code></pre>



## -struct-fields

