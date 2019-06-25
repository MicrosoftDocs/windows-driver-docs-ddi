---
UID: NS:d3dkmthk._D3DKMT_FREEGPUVIRTUALADDRESS
title: _D3DKMT_FREEGPUVIRTUALADDRESS (d3dkmthk.h)
description: D3DKMT_FREEGPUVIRTUALADDRESS is used with FreeGpuVirtualAddress to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.
old-location: display\d3dkmt_freegpuvirtualaddress.htm
ms.assetid: BB3DD49B-7DAB-48AC-BC63-595A184374AB
ms.date: 05/10/2018
ms.keywords: D3DKMT_FREEGPUVIRTUALADDRESS, D3DKMT_FREEGPUVIRTUALADDRESS structure [Display Devices], _D3DKMT_FREEGPUVIRTUALADDRESS, d3dkmthk/D3DKMT_FREEGPUVIRTUALADDRESS, display.d3dkmt_freegpuvirtualaddress
ms.topic: struct
req.header: d3dkmthk.h
req.include-header: D3dkmthk.h
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
- d3dkmthk.h
api_name:
- D3DKMT_FREEGPUVIRTUALADDRESS
product:
- Windows
targetos: Windows
tech.root: display
req.typenames: D3DKMT_FREEGPUVIRTUALADDRESS
---

# _D3DKMT_FREEGPUVIRTUALADDRESS structure


## -description


<b>D3DKMT_FREEGPUVIRTUALADDRESS</b> is used with <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtfreegpuvirtualaddress">FreeGpuVirtualAddress</a> to release a range of graphics processing unit (GPU) virtual addresses that were previously reserved or mapped.


## -struct-fields




### -field hAdapter

Specifies the handle to the adapter.


### -field BaseAddress

Specifies the base virtual address, in bytes, of the range to free. Must be aligned to 4 KB.


### -field Size

Specifies the size, in bytes, of the range to free. Must be aligned to 4 KB.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dkmthk/nf-d3dkmthk-d3dkmtfreegpuvirtualaddress">FreeGpuVirtualAddress</a>
 

 

