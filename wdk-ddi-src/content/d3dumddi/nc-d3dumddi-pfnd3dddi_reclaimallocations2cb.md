---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONS2CB
title: PFND3DDDI_RECLAIMALLOCATIONS2CB (d3dumddi.h)
description: pfnReclaimAllocations2Cb is called by the user mode driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocations2cb.htm
tech.root: display
ms.assetid: 1D3439BA-AB3D-4D94-B4C8-91BE9B3349A1
ms.date: 05/10/2018
keywords: ["PFND3DDDI_RECLAIMALLOCATIONS2CB callback function"]
ms.keywords: PFND3DDDI_RECLAIMALLOCATIONS2CB, d3dumddi/pfnReclaimAllocations2Cb, display.pfnreclaimallocations2cb, pfnReclaimAllocations2Cb, pfnReclaimAllocations2Cb callback, pfnReclaimAllocations2Cb callback function [Display Devices]
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Desktop
req.target-min-winverclnt: Windows 10
req.target-min-winversvr: Windows Server 2016
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
req.typenames: 
f1_keywords:
 - "d3dumddi/pfnReclaimAllocations2Cb"
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnReclaimAllocations2Cb
product:
 - Windows
---

# PFND3DDDI_RECLAIMALLOCATIONS2CB callback function

## -description

<b>pfnReclaimAllocations2Cb</b> is called by the user mode driver   to reclaim video memory allocations that were previously offered  for reuse.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_reclaimallocations2">D3DDDICB_RECLAIMALLOCATIONS2</a> structure that defines the allocations to reclaim.

## -returns

Returns one of the following values.

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The allocations were successfully reclaimed. | 
| **E_INVALIDARG** | An invalid parameter was supplied. | 
| **D3DDDIERR_DEVICEREMOVED** | The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.
Note  If this error code is returned, the driver's calling function (typically the [pfnReclaimResources](https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions)  routine) must return this error code to the Direct3D runtime. |

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_reclaimallocations2">D3DDDICB_RECLAIMALLOCATIONS2</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">pfnReclaimResources</a>

