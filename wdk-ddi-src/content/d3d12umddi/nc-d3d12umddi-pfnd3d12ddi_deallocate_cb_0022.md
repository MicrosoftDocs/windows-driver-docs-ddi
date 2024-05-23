---
UID: NC:d3d12umddi.PFND3D12DDI_DEALLOCATE_CB_0022
title: PFND3D12DDI_DEALLOCATE_CB_0022 (d3d12umddi.h)
description: Learn more about the PFND3D12DDI_DEALLOCATE_CB_0022 callback function.
ms.date: 05/22/2024
keywords: ["PFND3D12DDI_DEALLOCATE_CB_0022 callback function"]
ms.keywords: PFND3D12DDI_DEALLOCATE_CB_0022, PFND3D12DDI_DEALLOCATE_CB_0022 callback, d3d12umddi/pfnDeallocateCb, display.pfnd3d12ddi_deallocate_cb_0022, pfnDeallocateCb, pfnDeallocateCb callback function [Display Devices]
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
targetos: Windows
tech.root: display
req.typenames: 
f1_keywords:
 - PFND3D12DDI_DEALLOCATE_CB_0022
 - d3d12umddi/PFND3D12DDI_DEALLOCATE_CB_0022
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - PFND3D12DDI_DEALLOCATE_CB_0022
---

# PFND3D12DDI_DEALLOCATE_CB_0022 callback function

## -description

The D3D12 runtime's **pfnDeallocateCb** callback function controls resource deallocation.

## -parameters

### -param unnamedParam1

[in] The handle to the runtime's device.

### -param unnamedParam2

[in] Pointer to a [**D3D12DDICB_DEALLOCATE_0022**](ns-d3d12umddi-d3d12ddicb_deallocate_0022.md) structure that contains information for a deallocation.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

This callback function is used by the driver to request the Direct3D runtime to allocate resources.

Access this callback function by using the [**D3D12DDI_CORELAYER_DEVICECALLBACKS_0022**](ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md) structure.

The driver must check the return value of the function.

## -see-also

[**D3D12DDICB_DEALLOCATE_0022**](ns-d3d12umddi-d3d12ddicb_deallocate_0022.md)

[**D3D12DDI_CORELAYER_DEVICECALLBACKS_0022**](ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022.md)

[**pfnAllocateCb**](nc-d3d12umddi-pfnd3d12ddi_allocate_cb_0022.md)
