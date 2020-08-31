---
UID: NS:d3d10umddi.D3D10_DDI_SAMPLER_DESC
title: D3D10_DDI_SAMPLER_DESC (d3d10umddi.h)
description: The D3D10_DDI_SAMPLER_DESC structure describes a sampler.
old-location: display\d3d10_ddi_sampler_desc.htm
ms.assetid: 2f65b381-bf81-45b5-9583-793e4ffb453c
ms.date: 05/10/2018
keywords: ["D3D10_DDI_SAMPLER_DESC structure"]
ms.keywords: D3D10_DDI_SAMPLER_DESC, D3D10_DDI_SAMPLER_DESC structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3bd0d5fd-417c-43ef-9bdf-0073d8651ced.xml, d3d10umddi/D3D10_DDI_SAMPLER_DESC, display.d3d10_ddi_sampler_desc
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
tech.root: display
req.typenames: D3D10_DDI_SAMPLER_DESC
f1_keywords:
 - D3D10_DDI_SAMPLER_DESC
 - d3d10umddi/D3D10_DDI_SAMPLER_DESC
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10_DDI_SAMPLER_DESC
---

# D3D10_DDI_SAMPLER_DESC structure


## -description

The D3D10_DDI_SAMPLER_DESC structure describes a sampler.

## -struct-fields

### -field Filter

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_filter">D3D10_DDI_FILTER</a>-typed value that indicates the filter property for a sampler.

### -field AddressU

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_texture_address_mode">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>-typed value that indicates the texture-address mode for the u coordinate.

### -field AddressV

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_texture_address_mode">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>-typed value that indicates the texture-address mode for the v coordinate.

### -field AddressW

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_texture_address_mode">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>-typed value that indicates the texture-address mode for the w coordinate.

### -field MipLODBias

[in] A single-precision float that affects the level that the driver selects for MIP-map level of detail (LOD).

### -field MaxAnisotropy

[in] The maximum valid value for the anisotropy texture-stage state.

### -field ComparisonFunc

[in] A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_comparison_func">D3D10_DDI_COMPARISON_FUNC</a>-typed value that indicates the sampler-comparison function to perform.

### -field BorderColor

[in] A four-element array of single-precision float vectors for RGBA, where Red == 0. The border color is used when the D3D10_DDI_TEXTURE_ADDRESS_BORDER value is specified in the <b>AddressU</b>, <b>AddressV</b>, or <b>AddressW</b> member. The float should be converted to the appropriate resource format.

### -field MinLOD

[in] A single-precision float vector for the minimum level of detail (LOD) for the sampler.

### -field MaxLOD

[in] A single-precision float vector for the maximum level of detail (LOD) for the sampler.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_calcprivatesamplersize">CalcPrivateSamplerSize</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/nc-d3d10umddi-pfnd3d10ddi_createsampler">CreateSampler</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_comparison_func">D3D10_DDI_COMPARISON_FUNC</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_filter">D3D10_DDI_FILTER</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d10umddi/ne-d3d10umddi-d3d10_ddi_texture_address_mode">D3D10_DDI_TEXTURE_ADDRESS_MODE</a>

