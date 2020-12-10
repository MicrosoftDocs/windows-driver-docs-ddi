---
UID: NC:d3dumddi.PFND3DDDI_RECLAIMALLOCATIONS3CB
title: PFND3DDDI_RECLAIMALLOCATIONS3CB (d3dumddi.h)
description: pfnReclaimAllocations3Cb is called by the user mode driver to reclaim video memory allocations that were previously offered for reuse.
old-location: display\pfnreclaimallocations3cb.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["PFND3DDDI_RECLAIMALLOCATIONS3CB callback function"]
ms.keywords: PFND3DDDI_RECLAIMALLOCATIONS3CB, PFND3DDDI_RECLAIMALLOCATIONS3CB callback, d3dumddi/pfnReclaimAllocations3Cb, display.pfnreclaimallocations3cb, pfnReclaimAllocations3Cb, pfnReclaimAllocations3Cb callback function [Display Devices]
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
 - PFND3DDDI_RECLAIMALLOCATIONS3CB
 - d3dumddi/PFND3DDDI_RECLAIMALLOCATIONS3CB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnReclaimAllocations3Cb
product:
 - Windows
---

# PFND3DDDI_RECLAIMALLOCATIONS3CB callback function


## -description

<b>pfnReclaimAllocations3Cb</b> is called by the user mode driver   to reclaim video memory allocations that were previously offered  for reuse.

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in, out]

A pointer to a <a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocations3cb">D3DDDICB_RECLAIMALLOCATIONS3</a> structure that defines the allocations to reclaim. The previously used discarded array is replaced by a pResults member in this iteration.

## -returns

Returns one of the following values.

| **Return code** | **Description** | 
|:--|:--|
| **S_OK** | The allocations were successfully reclaimed. | 
| **E_INVALIDARG** | An invalid parameter was supplied. | 
| **D3DDDIERR_DEVICEREMOVED** | The video memory manager or display miniport driver could not complete the operation because either a Plug and Play (PnP) Stop event or a Timeout Detection and Recovery (TDR) event occurred.<br.>**Note:** If this error code is returned, the driver's calling function (typically the [pfnReclaimResources](../dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions.md)  routine) must return this error code to the Direct3D runtime. |

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_reclaimallocations3cb">D3DDDICB_RECLAIMALLOCATIONS3</a>



<a href="/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddi_devicecallbacks">D3DDDI_DEVICECALLBACKS</a>



<a href="/windows-hardware/drivers/ddi/dxgiddi/ns-dxgiddi-dxgi1_2_ddi_base_functions">pfnReclaimResources</a>
