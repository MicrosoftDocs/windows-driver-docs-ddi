---
UID: NC:d3d12umddi.PFND3D12DDI_DEALLOCATE_CB_0022
title: PFND3D12DDI_DEALLOCATE_CB_0022 (d3d12umddi.h)
description: The pfnDeallocateCb callback function controls heap deallocation by using a D3D12DDICB_DEALLOCATE_0022 structure.
old-location: display\pfnd3d12ddi_deallocate_cb_0022.htm
ms.date: 05/10/2018
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

The <i>pfnDeallocateCb</i> callback function controls heap deallocation by using a <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddicb_deallocate_0022">D3D12DDICB_DEALLOCATE_0022</a> structure.

## -parameters

### -param unnamedParam1

The handle to a device.

### -param unnamedParam2

A  <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddicb_deallocate_0022">D3D12DDICB_DEALLOCATE_0022</a> structure that contains information for a deallocation.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -remarks

Access this callback function by using the <a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddicb_deallocate_0022">D3D12DDICB_DEALLOCATE_0022</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>



<a href="/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_allocate_cb_0022">pfnAllocateCb</a>

