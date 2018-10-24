---
UID: NC:d3dkmddi.DXGKCB_MAPCONTEXTALLOCATION
title: DXGKCB_MAPCONTEXTALLOCATION
author: windows-driver-content
description: Maps a graphics processing unit (GPU) virtual address to the specified context allocation.
old-location: display\dxgkcbmapcontextallocation.htm
ms.assetid: 8EAC322D-B666-428A-99A3-96E489611832
ms.date: 05/10/2018
ms.keywords: DXGKCB_MAPCONTEXTALLOCATION, DXGKCB_MAPCONTEXTALLOCATION callback, DxgkCbMapContextAllocation, DxgkCbMapContextAllocation callback function [Display Devices], d3dkmddi/DxgkCbMapContextAllocation, display.dxgkcbmapcontextallocation
ms.topic: callback
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
-	d3dkmddi.h
api_name:
-	DxgkCbMapContextAllocation
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: 
---

# DXGKCB_MAPCONTEXTALLOCATION callback function


## -description


Maps a graphics processing unit (GPU) virtual address to the specified context allocation. This device driver interface (DDI) behaves like its user mode counterpart, see <a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a> for more details.


## -parameters




### -param hAdapter [in]

A handle to the display adapter.


### -param pArgs [in]

The <a href="https://msdn.microsoft.com/library/windows/hardware/dn906818">DXGKARGCB_MAPCONTEXTALLOCATION</a> structure that describes the operation.


## -returns




      Returns a <b>D3DGPU_VIRTUAL_ADDRESS</b> if successful, <b>NULL</b> otherwise.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/dn906818">DXGKARGCB_MAPCONTEXTALLOCATION</a>



<a href="https://msdn.microsoft.com/DA67A98C-BE9C-412D-9382-CAC5B05FEE3B">pfnMapGpuVirtualAddressCb</a>
 

 

