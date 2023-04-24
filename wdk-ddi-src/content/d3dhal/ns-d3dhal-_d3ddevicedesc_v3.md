---
UID: NS:d3dhal._D3DDeviceDesc_V3
title: D3DDeviceDesc_V3 (d3dhal.h)
description: The D3DDEVICEDESC_V3 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo.
old-location: display\d3ddevicedesc_v3.htm
tech.root: display
ms.date: 02/28/2023
keywords: ["D3DDeviceDesc_V3 structure"]
ms.keywords: "*LPD3DDEVICEDESC_V3, D3DDEVICEDESC_V3, D3DDEVICEDESC_V3 structure [Display Devices], _D3DDeviceDesc_V3, d3dhal/, d3dstrct_ae7c0a55-4597-4272-9b06-bc74a8340842.xml, display.d3ddevicedesc_v3"
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
req.typenames: D3DDEVICEDESC_V3, *LPD3DDEVICEDESC_V3
f1_keywords:
 - _D3DDeviceDesc_V3
 - d3dhal/_D3DDeviceDesc_V3
 - LPD3DDEVICEDESC_V3
 - d3dhal/LPD3DDEVICEDESC_V3
 - D3DDEVICEDESC_V3
 - d3dhal/D3DDEVICEDESC_V3
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - _D3DDeviceDesc_V3
 - LPD3DDEVICEDESC_V3
 - D3DDEVICEDESC_V3
---

# D3DDeviceDesc_V3 structure

## -description

The **D3DDeviceDesc_V3** structure is obsolete; only [**D3DDeviceDesc_V1**](ns-d3dhal-_d3ddevicedesc_v1.md) should be used.

The **D3DDeviceDesc_V3** structure contains fields that are already reported in the [**D3DHAL_D3DEXTENDEDCAPS**](ns-d3dhal-_d3dhal_d3dextendedcaps.md) structure when responding to the GUID_D3DExtendedCaps GUID in [**DdGetDriverInfo**](/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo).

## -struct-fields

### -field dwSize

### -field dwFlags

### -field dcmColorModel

### -field dwDevCaps

### -field dtcTransformCaps

### -field bClipping

### -field dlcLightingCaps

### -field dpcLineCaps

### -field dpcTriCaps

### -field dwDeviceRenderBitDepth

### -field dwDeviceZBufferBitDepth

### -field dwMaxBufferSize

### -field dwMaxVertexCount

### -field dwMinTextureWidth

### -field dwMinTextureHeight

### -field dwMaxTextureWidth

### -field dwMaxTextureHeight

### -field dwMinStippleWidth

### -field dwMaxStippleWidth

### -field dwMinStippleHeight

### -field dwMaxStippleHeight

### -field dwMaxTextureRepeat

### -field dwMaxTextureAspectRatio

### -field dwMaxAnisotropy

### -field dvGuardBandLeft

### -field dvGuardBandTop

### -field dvGuardBandRight

### -field dvGuardBandBottom

### -field dvExtentsAdjust

### -field dwStencilCaps

### -field dwFVFCaps

### -field dwTextureOpCaps

### -field wMaxTextureBlendStages

### -field wMaxSimultaneousTextures
