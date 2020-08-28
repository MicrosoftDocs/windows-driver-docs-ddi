---
UID: NC:d3dumddi.PFND3DDDI_FREEGPUVIRTUALADDRESSCB
title: PFND3DDDI_FREEGPUVIRTUALADDRESSCB (d3dumddi.h)
description: pfnFreeGpuVirtualAddressCb releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped.
old-location: display\pfnfreegpuvirtualaddresscb.htm
tech.root: display
ms.assetid: 92F2A43C-699B-4580-8A56-472D837A76E2
ms.date: 05/10/2018
keywords: ["PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback function"]
ms.keywords: PFND3DDDI_FREEGPUVIRTUALADDRESSCB, PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback, d3dumddi/pfnFreeGpuVirtualAddressCb, display.pfnfreegpuvirtualaddresscb, pfnFreeGpuVirtualAddressCb, pfnFreeGpuVirtualAddressCb callback function [Display Devices]
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
 - PFND3DDDI_FREEGPUVIRTUALADDRESSCB
 - d3dumddi/PFND3DDDI_FREEGPUVIRTUALADDRESSCB
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - d3dumddi.h
api_name:
 - pfnFreeGpuVirtualAddressCb
product:
 - Windows
---

# PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback function


## -description

<b>pfnFreeGpuVirtualAddressCb</b> releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped. 

The callback is a synchronous operation. The freed virtual address should not be accessed immediately after the call. If there are outstanding <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb">pfnMapGpuVirtualAddressCb</a> and <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb">pfnUpdateGpuVirtualAddressCb</a> operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.

The user mode driver  must ensure that no allocation, which is used for current rendering operations, is mapped to the address range.


<div class="alert"><b>Note</b>  When an allocation is freed through <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a> all outstanding GPU virtual addresses are automatically released.</div>
<div> </div>

## -parameters

### -param hDevice

A handle to the display device.

### -param Arg2

*pData* [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_freegpuvirtualaddress">D3DDDICB_FREEGPUVIRTUALADDRESS</a> structure that describes the operation to perform.

## -returns

If this callback function succeeds, it returns **S_OK**. Otherwise, it returns an **HRESULT** error code.

## -see-also

<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/ns-d3dumddi-_d3dddicb_freegpuvirtualaddress">D3DDDICB_FREEGPUVIRTUALADDRESS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_deallocatecb">pfnDeallocateCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb">pfnMapGpuVirtualAddressCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dumddi/nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb">pfnUpdateGpuVirtualAddressCb</a>

