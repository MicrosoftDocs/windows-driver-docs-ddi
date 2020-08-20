---
UID: NC:d3d12umddi.PFND3D12DDI_ALLOCATE_CB_0022
title: PFND3D12DDI_ALLOCATE_CB_0022 (d3d12umddi.h)
description: The pfnAllocateCb callback function controls heap allocation by using a D3D12DDICB_ALLOCATE_0022 value.
old-location: display\pfnd3d12ddi_allocate_cb_0022.htm
ms.assetid: D0326C98-F187-4F62-AE60-60F0B38AB0D4
ms.date: 05/10/2018
keywords: ["PFND3D12DDI_ALLOCATE_CB_0022 callback function"]
ms.keywords: PFND3D12DDI_ALLOCATE_CB_0022, PFND3D12DDI_ALLOCATE_CB_0022 callback, d3d12umddi/pfnAllocateCb, display.pfnd3d12ddi_allocate_cb_0022, pfnAllocateCb, pfnAllocateCb callback function [Display Devices]
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
 - "d3d12umddi/pfnAllocateCb"
 - "pfnAllocateCb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - D3d12umddi.h
api_name:
 - pfnAllocateCb
product:
 - Windows
---

# PFND3D12DDI_ALLOCATE_CB_0022 callback function

## -description

The <i>pfnAllocateCb</i> callback function controls heap allocation by using a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddicb_allocate_0022">D3D12DDICB_ALLOCATE_0022</a> value.

## -parameters

### -param Arg1

The handle for a device.

### -param Arg2

A <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddicb_allocate_0022">D3D12DDICB_ALLOCATE_0022</a> structure that contains information for an allocation.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an HRESULT error code.

## -remarks

Access this callback function by using the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a> structure.

The driver must check the return value of the function.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddicb_allocate_0022">D3D12DDICB_ALLOCATE_0022</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/ns-d3d12umddi-d3d12ddi_corelayer_devicecallbacks_0022">D3D12DDI_CORELAYER_DEVICECALLBACKS_0022</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3d12umddi/nc-d3d12umddi-pfnd3d12ddi_deallocate_cb_0022">pfnDeallocateCb</a>

