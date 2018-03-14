---
UID: NC:d3dumddi.PFND3DDDI_FREEGPUVIRTUALADDRESSCB
title: PFND3DDDI_FREEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnFreeGpuVirtualAddressCb releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped.
old-location: display\pfnfreegpuvirtualaddresscb.htm
old-project: display
ms.assetid: 92F2A43C-699B-4580-8A56-472D837A76E2
ms.author: windowsdriverdev
ms.date: 2/26/2018
ms.keywords: PFND3DDDI_FREEGPUVIRTUALADDRESSCB, d3dumddi/pfnFreeGpuVirtualAddressCb, display.pfnfreegpuvirtualaddresscb, pfnFreeGpuVirtualAddressCb, pfnFreeGpuVirtualAddressCb callback function [Display Devices]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	UserDefined
api_location:
-	d3dumddi.h
api_name:
-	pfnFreeGpuVirtualAddressCb
product: Windows
targetos: Windows
req.typenames: DXGK_PTE
---

# PFND3DDDI_FREEGPUVIRTUALADDRESSCB callback


## -description


<b>pfnFreeGpuVirtualAddressCb</b> releases a range of graphics processing unit (GPU) virtual addresses that was previously reserved or mapped. 

The callback is a synchronous operation. The freed virtual address should not be accessed immediately after the call. If there are outstanding <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a> and <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a> operations, which reference the virtual address, they will be ignored after the virtual address is freed. A new virtual address range can be allocated in place of the freed one immediately after return from the function.

The user mode driver  must ensure that no allocation, which is used for current rendering operations, is mapped to the address range.


<div class="alert"><b>Note</b>  When an allocation is freed through <a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a> all outstanding GPU virtual addresses are automatically released.</div>
<div> </div>



## -prototype


````
PFND3DDDI_FREEGPUVIRTUALADDRESSCB pfnFreeGpuVirtualAddressCb;

HRESULT APIENTRY CALLBACK* pfnFreeGpuVirtualAddressCb(
  _In_       HANDLE                         hDevice,
  _In_ const D3DDDICB_FREEGPUVIRTUALADDRESS *pData
)
{ ... }
````


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








#### - pData [in]

A pointer to a <a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_freegpuvirtualaddress.md">D3DDDICB_FREEGPUVIRTUALADDRESS</a> structure that describes the operation to perform.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also

<a href="..\d3dumddi\ns-d3dumddi-_d3dddicb_freegpuvirtualaddress.md">D3DDDICB_FREEGPUVIRTUALADDRESS</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_mapgpuvirtualaddresscb.md">pfnMapGpuVirtualAddressCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_deallocatecb.md">pfnDeallocateCb</a>



<a href="..\d3dumddi\nc-d3dumddi-pfnd3dddi_updategpuvirtualaddresscb.md">pfnUpdateGpuVirtualAddressCb</a>



 

 


