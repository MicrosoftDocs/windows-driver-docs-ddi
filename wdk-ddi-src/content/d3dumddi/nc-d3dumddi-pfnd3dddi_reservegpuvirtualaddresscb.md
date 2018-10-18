---
UID: NC:d3dumddi.PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
title: PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB
author: windows-driver-content
description: pfnReserveGPUVirtualAddressCb reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.
old-location: display\pfnreservegpuvirtualaddresscb.htm
tech.root: display
ms.assetid: CEDE03E1-4B0D-4839-B7D6-0826CC103C5E
ms.date: 5/10/2018
ms.keywords: PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB, PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB callback, d3dumddi/pfnReserveGpuVirtualAddressCb, display.pfnreservegpuvirtualaddresscb, pfnReserveGpuVirtualAddressCb, pfnReserveGpuVirtualAddressCb callback function [Display Devices]
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
-	pfnReserveGpuVirtualAddressCb
product:
- Windows
targetos: Windows
req.typenames: 
---

# PFND3DDDI_RESERVEGPUVIRTUALADDRESSCB callback function


## -description


<b>pfnReserveGPUVirtualAddressCb</b> reserves an address range in the current process graphics processing unit (GPU) virtual address space. The address range is only reserved, there is no actual memory behind it.


The user mode driver may choose the base GPU virtual address to use for the reservation by specifying a non-NULL value for <b>BaseAddress</b>. The video memory manager will use the specified range if it is available. If the range intersects with an existing range, the operation will fail. The user mode driver may pass a <b>NULL</b><b>BaseAddress</b> to let the video memory manager pick a base address.

When the user mode driver chooses to let the video memory manager pick a base address for the GPU virtual address range, it may choose to constrain the range that the video memory manager will consider by specifying non-NULL values for <b>MinimumAddress</b> and <b>MaximumAddress</b>. The video memory manager will ensure that the allocated GPU virtual address range is entirely contained in the range. The user mode driver may specify only a <b>MinimumAddress</b> (<b>MaximumAddress</b> being assumed to be the end of the address space) or only specify a <b>MaximumAddress</b> (<b>MinimumAddress</b> being assumed to be 0).

  


## -parameters




### -param hDevice [in]

A handle to the display device.


### -param *








*pData* [in, out]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/dn906327">D3DDDI_RESERVEGPUVIRTUALADDRESS</a> structure that describes the operation to perform.




## -returns



If this callback function succeeds, it returns <b xmlns:loc="http://microsoft.com/wdcml/l10n">S_OK</b>. Otherwise, it returns an <b xmlns:loc="http://microsoft.com/wdcml/l10n">HRESULT</b> error code.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906327">D3DDDI_RESERVEGPUVIRTUALADDRESS</a>
 

 

