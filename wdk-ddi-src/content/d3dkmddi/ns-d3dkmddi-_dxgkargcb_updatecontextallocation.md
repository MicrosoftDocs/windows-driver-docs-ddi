---
UID: NS:d3dkmddi._DXGKARGCB_UPDATECONTEXTALLOCATION
title: _DXGKARGCB_UPDATECONTEXTALLOCATION (d3dkmddi.h)
description: DXGKARGCB_UPDATECONTEXTALLOCATION contains the data used to call DxgkCbUpdateContextAllocation.
old-location: display\dxgkargcb_updatecontextallocation.htm
ms.assetid: 07BFCA6C-4E75-4BB5-9F6A-22E1FFAFFF6F
ms.date: 05/10/2018
ms.keywords: DXGKARGCB_UPDATECONTEXTALLOCATION, DXGKARGCB_UPDATECONTEXTALLOCATION structure [Display Devices], _DXGKARGCB_UPDATECONTEXTALLOCATION, d3dkmddi/DXGKARGCB_UPDATECONTEXTALLOCATION, display.dxgkargcb_updatecontextallocation
ms.topic: struct
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
req.target-type: Windows
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dkmddi.h
api_name:
- DXGKARGCB_UPDATECONTEXTALLOCATION
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: DXGKARGCB_UPDATECONTEXTALLOCATION
---

# _DXGKARGCB_UPDATECONTEXTALLOCATION structure


## -description


<b>DXGKARGCB_UPDATECONTEXTALLOCATION</b> contains the data used to call <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_updatecontextallocation">DxgkCbUpdateContextAllocation</a>.


## -struct-fields




### -field hAllocation

Handle to the context allocation being updated. The allocation defines a physical adapter in a linked display adapter link.


### -field pPrivateDriverData

Pointer to a private driver data buffer to be passed to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_updatecontextallocation">DxgkCbUpdateContextAllocation</a> paging operation.


### -field PrivateDriverDataSize

Specify the size of the driver private data.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmddi/nc-d3dkmddi-dxgkcb_updatecontextallocation">DxgkCbUpdateContextAllocation</a>
 

 

