---
UID: NC:d3d10umddi.PFND3DWDDM2_0DDI_CREATEUNORDEREDACCESSVIEW
tech.root: display
title: PFND3DWDDM2_0DDI_CREATEUNORDEREDACCESSVIEW
ms.date: 06/02/2023
targetos: Windows
description: Learn more about the CreateUnorderedAccessView function.
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
 - PFND3DWDDM2_0DDI_CREATEUNORDEREDACCESSVIEW
f1_keywords:
 - PFND3DWDDM2_0DDI_CREATEUNORDEREDACCESSVIEW
 - d3d10umddi/PFND3DWDDM2_0DDI_CREATEUNORDEREDACCESSVIEW
dev_langs:
 - c++
helpviewer_keywords:
 - PFND3DWDDM2_0DDI_CREATEUNORDEREDACCESSVIEW
---

## -description

**CreateUnorderedAccessView(WDDM 2.0)** creates an unordered access view.

## -parameters

### -param unnamedParam1

[in] **hDevice** is a handle to the display device (graphics context).

### -param unnamedParam2

[in] **pCreateUnorderedAccessView** is a pointer to a [**D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createunorderedaccessview.md) structure that describes the parameters that the user-mode display driver uses to create an unordered access view.

### -param unnamedParam3

[in] **hUnorderedAccessView** is a handle to the driver's private data for the unordered access view.

### -param unnamedParam4

[in] **hRTUnorderedAccessView** is a handle to the unordered access view that the driver should use when it calls back into the Direct3D runtime.

## -remarks

The driver might run out of memory. Therefore, the driver can pass E_OUTOFMEMORY or D3DDDIERR_DEVICEREMOVED in a call to the [**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md) function. The Direct3D runtime determines that any other errors are critical. If the driver passes any errors, which includes D3DDDIERR_DEVICEREMOVED, the Direct3D runtime determines that the handle is invalid; therefore, the runtime does not call the [**DestroyUnorderedAccessView**](nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md) function to destroy the handle that the **hUnorderedAccessView** parameter specifies.

## -see-also

[**CalcPrivateUnorderedAccessViewSize (WDDM 2.0)**](nc-d3d10umddi-pfnd3dwddm2_0ddi_calcprivateunorderedaccessviewsize.md)

[**D3DWDDM2_0DDIARG_CREATEUNORDEREDACCESSVIEW**](ns-d3d10umddi-d3dwddm2_0ddiarg_createunorderedaccessview.md)

[**DestroyUnorderedAccessView**](nc-d3d10umddi-pfnd3d11ddi_destroyunorderedaccessview.md)

[**D3D11DDI_DEVICEFUNCS**](ns-d3d10umddi-d3d11ddi_devicefuncs.md)

[**pfnSetErrorCb**](nc-d3d10umddi-pfnd3d10ddi_seterror_cb.md)
