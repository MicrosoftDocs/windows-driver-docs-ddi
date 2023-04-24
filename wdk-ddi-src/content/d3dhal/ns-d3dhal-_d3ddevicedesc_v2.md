---
UID: NS:d3dhal._D3DDeviceDesc_V2
title: D3DDeviceDesc_V2 (d3dhal.h)
description: The D3DDEVICEDESC_V2 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo.
old-location: display\d3ddevicedesc_v2.htm
tech.root: display
ms.date: 02/28/2023
keywords: ["D3DDeviceDesc_V2 structure"]
ms.keywords: "*LPD3DDEVICEDESC_V2, D3DDEVICEDESC_V2, D3DDEVICEDESC_V2 structure [Display Devices], _D3DDeviceDesc_V2, d3dhal/, d3dstrct_93cd326d-38b8-4911-87de-a0b4e81f897c.xml, display.d3ddevicedesc_v2"
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
req.typenames: D3DDEVICEDESC_V2, *LPD3DDEVICEDESC_V2
f1_keywords:
 - _D3DDeviceDesc_V2
 - d3dhal/_D3DDeviceDesc_V2
 - LPD3DDEVICEDESC_V2
 - d3dhal/LPD3DDEVICEDESC_V2
 - D3DDEVICEDESC_V2
 - d3dhal/D3DDEVICEDESC_V2
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dhal.h
api_name:
 - _D3DDeviceDesc_V2
 - LPD3DDEVICEDESC_V2
 - D3DDEVICEDESC_V2
---

# D3DDeviceDesc_V2 structure

## -description

The **D3DDeviceDesc_V2** structure is obsolete; only [**D3DDeviceDesc_V1**](ns-d3dhal-_d3ddevicedesc_v1.md) should be used.

The **D3DDeviceDesc_V2** structure contains fields that are already reported in the [**D3DHAL_D3DEXTENDEDCAPS**](ns-d3dhal-_d3dhal_d3dextendedcaps.md) structure when responding to the GUID_D3DExtendedCaps GUID in [**DdGetDriverInfo**](/windows/win32/api/ddrawint/nc-ddrawint-pdd_getdriverinfo).

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
