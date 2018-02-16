---
UID: NS:d3dhal._D3DDeviceDesc_V2
title: "_D3DDeviceDesc_V2"
author: windows-driver-content
description: The D3DDEVICEDESC_V2 structure contains fields that are already reported in the D3DHAL_D3DEXTENDEDCAPS structure when responding to the GUID_D3DExtendedCaps GUID in DdGetDriverInfo.
old-location: display\d3ddevicedesc_v2.htm
old-project: display
ms.assetid: d8ef093e-81f9-443c-9d85-d0d1b6c03416
ms.author: windowsdriverdev
ms.date: 12/29/2017
ms.keywords: D3DDEVICEDESC_V2, d3dstrct_93cd326d-38b8-4911-87de-a0b4e81f897c.xml, display.d3ddevicedesc_v2, _D3DDeviceDesc_V2, *LPD3DDEVICEDESC_V2, d3dhal/, D3DDEVICEDESC_V2 structure [Display Devices]
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
-	D3DDEVICEDESC_V2
product: Windows
targetos: Windows
req.typenames: "*LPD3DDEVICEDESC_V2, D3DDEVICEDESC_V2"
---

# _D3DDeviceDesc_V2 structure


## -description


<b>The D3DDEVICEDESC_V2 structure is obsolete; only D3DDEVICEDESC_V1 should be used.</b>

The D3DDEVICEDESC_V2 structure contains fields that are already reported in the 
	 <a href="..\d3dhal\ns-d3dhal-_d3dhal_d3dextendedcaps.md">D3DHAL_D3DEXTENDEDCAPS</a> 
	 structure when responding to the GUID_D3DExtendedCaps GUID in <a href="https://msdn.microsoft.com/89a22163-a678-4c72-932a-ae4d17922e0b">DdGetDriverInfo</a>. 
	 


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

