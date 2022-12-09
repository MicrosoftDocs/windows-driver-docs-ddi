---
UID: NS:d3d10umddi.D3D10DDIARG_CREATERESOURCE
title: D3D10DDIARG_CREATERESOURCE (d3d10umddi.h)
description: The D3D10DDIARG_CREATERESOURCE structure describes the parameters that the user-mode display driver uses to create a resource.
old-location: display\d3d10ddiarg_createresource.htm
ms.date: 11/03/2022
ms.custom: content-health
keywords: ["D3D10DDIARG_CREATERESOURCE structure"]
ms.keywords: D3D10DDIARG_CREATERESOURCE, D3D10DDIARG_CREATERESOURCE structure [Display Devices], UMDisplayDriver_Dx10param_Structs_3f91ee50-2bdd-4206-afe6-d8b79d3b7d80.xml, d3d10umddi/D3D10DDIARG_CREATERESOURCE, display.d3d10ddiarg_createresource
req.header: d3d10umddi.h
req.include-header: D3d10umddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows Vista
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
req.typenames: D3D10DDIARG_CREATERESOURCE
f1_keywords:
 - D3D10DDIARG_CREATERESOURCE
 - d3d10umddi/D3D10DDIARG_CREATERESOURCE
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3D10DDIARG_CREATERESOURCE
---

# D3D10DDIARG_CREATERESOURCE structure

## -description

**D3D10DDIARG_CREATERESOURCE** contains the arguments used by [**PFND3D10DDI_CREATERESOURCE**](nc-d3d10umddi-pfnd3d10ddi_createresource.md) to create a resource.

## -struct-fields

### -field pMipInfoList [in]

An array of [**D3D10DDI_MIPINFO**](ns-d3d10umddi-d3d10ddi_mipinfo.md) structures that contains dimensions for MIP levels. For resource formats where a single pixel or texel cannot be referenced directly with a byte address, the dimensions of the physical resource are typically larger or equal to the texel dimensions, in order to satisfy the necessary space requirements. For example, to create a fully mipped BC1 Texture2D, where the most detailed level is 8x8, the **pMipInfoList** array is:  { { 8, 8, 1, 8, 8, 1 }, { 4, 4, 1, 4, 4, 1 }, { 2, 2, 1, 4, 4, 1 }, { 1, 1, 1, 4, 4, 1 } }.

### -field pInitialDataUP [in]

An array of [**D3D10_DDIARG_SUBRESOURCE_UP**](ns-d3d10umddi-d3d10_ddiarg_subresource_up.md) structures that provides initialization information for the resource's list of subresources.

### -field ResourceDimension [in]

A value of type [**D3D10DDIRESOURCE_TYPE**](/windows-hardware/drivers/display/ne-d3d10umddi-d3d10ddiresource_type) that indicates the resource type and dimensionality.

### -field Usage [in]

A value of type [**D3D10_DDI_RESOURCE_USAGE**](ne-d3d10umddi-d3d10_ddi_resource_usage.md) that indicates how the resource is used.

### -field BindFlags [in]

A valid bitwise OR of [**D3D10_DDI_RESOURCE_BIND_FLAG**](ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md) values that indicates how the resource is bound.

### -field MapFlags [in]

A value of type [**D3D10_DDI_MAP**](ne-d3d10umddi-d3d10_ddi_map.md) that indicates the access level to map to the resource.

### -field MiscFlags [in]

A valid bitwise OR of [**D3D10_DDI_RESOURCE_MISC_FLAG**](ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md) values that indicates miscellaneous information about the resource.

### -field Format [in]

A value of type [**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format) that indicates the pixel format of the resource.

### -field SampleDesc [in]

A value of type [**DXGI_SAMPLE_DESC**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_sample_desc) that describes the sample count and quality of the resource.

### -field MipLevels [in]

The number of MIP-map levels for the resource.

### -field ArraySize [in]

The number of array elements for a 2-D texture or 1-D texture. **ArraySize** must be set to 6 for a cube texture.

Beginning in Windows 8, if the driver must create a stereo back buffer, it should set this member to a value of 2.

### -field pPrimaryDesc [in, out]

A pointer to a [**DXGI_DDI_PRIMARY_DESC**](../dxgiddi/ns-dxgiddi-dxgi_ddi_primary_desc.md) structure that describes a resource that is used as a primary.

The Microsoft Direct3D runtime sets **pPrimaryDesc** to a non-NULL value only if the D3D10_DDI_BIND_PRESENT bit is set in the **BindFlags** member; however, even if D3D10_DDI_BIND_PRESENT is set, the runtime does not always set **pPrimaryDesc** to non-NULL. Setting **pPrimaryDesc** to non-NULL indicates that the runtime will use the created resource as a primary (that is, the resource is scanned out to the display) and in flip-style present operations.

The user-mode display driver can return the DXGI_DDI_PRIMARY_DRIVER_FLAG_NO_SCANOUT flag in the **DriverFlags** member of DXGI_DDI_PRIMARY_DESC to prevent the runtime from performing flip-style present operations.

If **pPrimaryDesc** is set to NULL, the runtime will use the created resource in copy-style (bit-block transfer) present operations.

## -see-also

[**CreateResource(D3D10)**](nc-d3d10umddi-pfnd3d10ddi_createresource.md)

[**D3D10DDIRESOURCE_TYPE**](/previous-versions/windows/hardware/drivers/ff541810(v=vs.85))

[**D3D10DDI_MIPINFO**](ns-d3d10umddi-d3d10ddi_mipinfo.md)

[**D3D10_DDIARG_SUBRESOURCE_UP**](ns-d3d10umddi-d3d10_ddiarg_subresource_up.md)

[**D3D10_DDI_MAP**](ne-d3d10umddi-d3d10_ddi_map.md)

[**D3D10_DDI_RESOURCE_BIND_FLAG**](ne-d3d10umddi-d3d10_ddi_resource_bind_flag.md)

[**D3D10_DDI_RESOURCE_MISC_FLAG**](ne-d3d10umddi-d3d10_ddi_resource_misc_flag.md)

[**D3D10_DDI_RESOURCE_USAGE**](ne-d3d10umddi-d3d10_ddi_resource_usage.md)

[**DXGI_DDI_PRIMARY_DESC**](../dxgiddi/ns-dxgiddi-dxgi_ddi_primary_desc.md)

[**DXGI_FORMAT**](/windows/win32/api/dxgiformat/ne-dxgiformat-dxgi_format)

[**DXGI_SAMPLE_DESC**](/windows/win32/api/dxgicommon/ns-dxgicommon-dxgi_sample_desc)
