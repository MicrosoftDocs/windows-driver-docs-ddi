---
UID: NS:d3dhal._D3DDeviceDesc_V3
title: "_D3DDeviceDesc_V3"
author: windows-driver-content
description: The D3DDEVICEDESC_V3 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo.
old-location: display\d3ddevicedesc_v3.htm
old-project: display
ms.assetid: 36a7b29a-f744-42c8-9e60-9b5dbba3a32f
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: d3dhal/, D3DDEVICEDESC_V3, *LPD3DDEVICEDESC_V3, _D3DDeviceDesc_V3, display.d3ddevicedesc_v3, d3dstrct_ae7c0a55-4597-4272-9b06-bc74a8340842.xml, D3DDEVICEDESC_V3 structure [Display Devices]
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
-	D3DDEVICEDESC_V3
product: Windows
targetos: Windows
req.typenames: D3DDEVICEDESC_V3, *LPD3DDEVICEDESC_V3
---

# _D3DDeviceDesc_V3 structure


## -description


<b>The D3DDEVICEDESC_V3 structure is obsolete; only D3DDEVICEDESC_V1 should be used.</b>

The D3DDEVICEDESC_V3 structure contains fields that are already reported in the <a href="..\d3dhal\ns-d3dhal-_d3dhal_d3dextendedcaps.md">D3DHAL_D3DEXTENDEDCAPS</a> structure when responding to the GUID_D3DExtendedCaps GUID in <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>.


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

