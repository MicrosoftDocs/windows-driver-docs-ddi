---
UID: NS:d3d12umddi.D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020
title: D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020
author: windows-driver-content
description: Specifies values for luma keying.
old-location: display\d3d12ddi_video_process_luma_key.htm
old-project: display
ms.assetid: 79D8C170-A562-45F4-834B-58D8F7490C36
ms.author: windowsdriverdev
ms.date: 2/22/2018
ms.keywords: ",  , ,, 0, 1, 2, 3, A, C, D, D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020, D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020 structure [Display Devices], E, I, K, L, M, O, P, R, S, U, V, Y, _, d3d12umddi/D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020, display.d3d12ddi_video_process_luma_key"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: d3d12umddi.h
req.include-header: D3d12umddi.h
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
-	D3d12umddi.h
apiname:
-	D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020
product: Windows
targetos: Windows
req.typenames: D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020
---

# D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020 structure


## -description


Specifies values for luma keying.


## -syntax


````
typedef struct D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020 {
  BOOL  Enable;
  FLOAT Lower;
  FLOAT Upper;
} D3D12DDI_VIDEO_PROCESS_LUMA_KEY_0020;
````


## -struct-fields




### -field Enable

Whether luma keying is enabled.


### -field Lower

The lower bound for the luma key. The valid range is from 0 to 1. If the <b>Enable</b> member is false, this value is ignored.


### -field Upper

The upper bound for the luma key. The valid range is from 0 to 1. If the <b>Enable</b> member is false, this value is ignored.


## -remarks



The values of <b>Lower</b> and <b>Upper</b> are the lower and upper bounds of the luma key. For a format that has <b>n</b> bits per channel, these values are converted to luma values as follows: <pre class="syntax" xml:space="preserve"><code>value = f * (( 1 &lt;&lt; n ) - 1 )</code></pre>


Any pixel whose luma value falls within the upper and lower bounds, inclusive, is treated as transparent.  For example, if the pixel format uses 8-bit luma, the upper bound is calculated as follows:<pre class="syntax" xml:space="preserve"><code>BYTE Y = BYTE( max ( min ( 1.0, Upper ), 0.0 ) * 255.0 )</code></pre>


The value is clamped to the range from 0 to 1 before multiplying by 255.



