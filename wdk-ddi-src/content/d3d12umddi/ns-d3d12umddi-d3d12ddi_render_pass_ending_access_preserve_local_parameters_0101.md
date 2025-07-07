---
UID: NS:d3d12umddi.D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
tech.root: display
title: D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
ms.date: 03/28/2025
targetos: Windows
description: Learn more about the D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101 structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d12umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10, version 1809
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d12umddi.h
api_name:
 - D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
f1_keywords:
 - D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
 - d3d12umddi/D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
dev_langs:
 - c++
helpviewer_keywords:
 - D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101
---

## -description

The **D3D12DDI_RENDER_PASS_ENDING_ACCESS_PRESERVE_LOCAL_PARAMETERS_0101** structure specifies parameters for preserving a local portion of a resource at the end of a render pass.

## -struct-fields

### -field AdditionalWidth

Specifies the additional width, in pixels, to be preserved on either side of the preserved region. A value of 0 means no extra pixels are preserved beyond the specified region. See Remarks.

### -field AdditionalHeight

Specifies the additional height, in pixels, to be preserved above and below the preserved region. A value of 0 means no extra pixels are preserved beyond the specified region. See Remarks.

## -remarks

This structure is used when the ending access [**Type**](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_0053.md) for a resource within a render pass is one of the following values. For each of these types, the beginning of the previous pass must specify the matching [**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053_PRESERVE_LOCAL_*XXX***](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type_0053.md) value and the same **AdditionalWidth**/**AdditionalHeight** parameters.

* **D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER**

* **D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_SRV**

* **D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_UAV**

**AdditionalWidth** and **AdditionalHeight** must be set to 0 for **D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0101_PRESERVE_LOCAL_RENDER** because they don't make sense in the context of rendering.

If **AdditionalWidth**/**AdditionalHeight** parameters for the pass are nonzero, they define a border of additional pixel locations around the current one that can also be read. For instance, **AdditionalWidth** of 1 and **AdditionalHeight** of 2 means a region 3 pixels wide and 5 pixels tall around the current pixel can be read by the current pixel.

For more information, see [D3D12 Render Passes](/windows-hardware/drivers/display/d3d12-render-passes).

## -see-also

[**D3D12DDI_RENDER_PASS_BEGINNING_ACCESS_TYPE_0053**](ne-d3d12umddi-d3d12ddi_render_pass_beginning_access_type_0053.md)

[**D3D12DDI_RENDER_PASS_ENDING_ACCESS_0053**](ns-d3d12umddi-d3d12ddi_render_pass_ending_access_0053.md)

[**D3D12DDI_RENDER_PASS_ENDING_ACCESS_TYPE_0053**](ne-d3d12umddi-d3d12ddi_render_pass_ending_access_type_0053.md)

[**pfnBeginRenderPass**](nc-d3d12umddi-pfnd3d12ddi_begin_render_pass_0053.md)
