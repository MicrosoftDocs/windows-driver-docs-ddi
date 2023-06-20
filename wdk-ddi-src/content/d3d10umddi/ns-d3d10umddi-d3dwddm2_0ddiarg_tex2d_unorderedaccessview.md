---
UID: NS:d3d10umddi.D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
tech.root: display
title: D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW structure.
prerelease: false
req.construct-type: structure
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.include-header: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.redist: 
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.target-type: 
req.typenames: D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
typedef_isUnnamed: false
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - HeaderDef
api_location:
 - d3d10umddi.h
api_name:
 - D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
f1_keywords:
 - D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
 - d3d10umddi/D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
dev_langs:
 - c++
helpviewer_keywords:
 - D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW
---

## -description

the **D3DWDDM2_0DDIARG_TEX2D_UNORDEREDACCESSVIEW** structure describes a 2D texture that is used to create an unordered access view in a call to [**CreateUnorderedAccessView (WDDM 2.0**](nc-d3d10umddi-pfnd3dwddm2_0ddi_createunorderedaccessview.md).

## -struct-fields

### -field MipSlice

[in] The identifier of the MIP-map slice.

### -field FirstArraySlice

[in] The identifier of the first array slice.

### -field ArraySize

[in] The number of array slices for the texture.

### -field PlaneSlice

[in] The identifier of the plane slice.

### -field PlaneIndex

[in] The index (plane slice number) of the plane to use in the texture.

## -remarks

If **MipLevels** is set to -1, the MIP-maps in the texture start from the MIP-map that is set in the **MostDetailedMip** member.

If **ArraySize** is set to -1, the array slices in the texture start from the array slice that is set in **FirstArraySlice** member.

## -see-also

[**CalcPrivateUnorderedAccessViewSize (WDDM 2.0**](nc-d3d10umddi-pfnd3dwddm2_0ddi_calcprivateunorderedaccessviewsize.md)

[**CreateUnorderedAccessView (WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_createunorderedaccessview.md)

[**D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createunorderedaccessview.md)
