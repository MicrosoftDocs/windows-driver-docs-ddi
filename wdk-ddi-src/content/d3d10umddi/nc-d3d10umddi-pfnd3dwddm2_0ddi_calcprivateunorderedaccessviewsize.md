---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
tech.root: display
title: PFND3DWDDM2_0DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the CalcPrivateUnorderedAccessViewSize function.
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
 - PFND3DWDDM2_0DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
f1_keywords:
 - PFND3DWDDM2_0DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
 - d3d10umddi/PFND3DWDDM2_0DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3DWDDM2_0DDI_CALCPRIVATEUNORDEREDACCESSVIEWSIZE
---

## -description

The **CalcPrivateUnorderedAccessViewSize** function determines the size of the user-mode display driver's private region of memory (that is, the size of internal driver structures, not the size of the resource video memory) for an unordered access view.

## -parameters

### -param unnamedParam1

[in] **hDevice** is a handle to the display device (graphics context).

### -param unnamedParam2

[in] **pCreateUnorderedAccessView** is a pointer to a [**D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createunorderedaccessview.md) structure that describes the parameters that the user-mode display driver uses to calculate the size of the memory region.

## -returns

**CalcPrivateUnorderedAccessViewSize** returns the size in bytes of the memory region that the driver requires to create an unordered access view.

## -see-also

[**D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createunorderedaccessview.md)

[**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md)
