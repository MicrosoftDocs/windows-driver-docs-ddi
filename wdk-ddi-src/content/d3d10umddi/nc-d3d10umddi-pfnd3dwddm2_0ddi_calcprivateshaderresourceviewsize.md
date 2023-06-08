---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
tech.root: display
title: PFND3DWDDM2_0DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the CalcPrivateShaderResourceViewSize function.
prerelease: false
req.assembly: 
req.construct-type: function
req.ddi-compliance: 
req.dll: 
req.header: d3d10umddi.h
req.idl: 
req.include-header: 
req.irql: 
req.kmdf-ver: 
req.lib: 
req.max-support: 
req.namespace: 
req.redist: 
req.target-min-winverclnt: Windows 10 (WDDM 2.0)
req.target-min-winversvr: 
req.target-type: 
req.type-library: 
req.umdf-ver: 
req.unicode-ansi: 
topic_type:
 - apiref
api_type:
 - LibDef
api_location:
 - d3d10umddi.h
api_name:
 - PFND3DWDDM2_0DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
f1_keywords:
 - PFND3DWDDM2_0DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
 - d3d10umddi/PFND3DWDDM2_0DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3DWDDM2_0DDI_CALCPRIVATESHADERRESOURCEVIEWSIZE
---

## -description

**CalcPrivateShaderResourceViewSize(WDDM 2.0)** determines the size of the user-mode display driver's (UMD's) private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for a shader resource view.

## -parameters

### -param unnamedParam1

[in] **hDevice** is a handle to the display device (graphics context).

### -param unnamedParam2

[in] **pCreateShaderResourceView** is a pointer to a [**D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createshaderresourceview.md) structure that describes the parameters that UMD uses to calculate the size of the memory region.

## -returns

**CalcPrivateShaderResourceViewSize(WDDM 2.0)** returns the size of the memory region that the driver requires to create a shader resource view.

## -see-also

[**CreateShaderResourceView(WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_createshaderresourceview.md)

[**D3DWDDM2_0DDIARG_CREATESHADERRESOURCEVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createshaderresourceview.md)
