---
UID: NS:d3dumddi._D3DDDICB_LOCK2
title: _D3DDDICB_LOCK2 (d3dumddi.h)
description: D3DDDICB_LOCK2 describes parameters for locking an allocation.
old-location: display\d3dddicb_lock2.htm
tech.root: display
ms.assetid: 71E2E98D-4C97-4C04-A379-88C2A7CC8428
ms.date: 05/10/2018
keywords: ["_D3DDDICB_LOCK2 structure"]
ms.keywords: D3DDDICB_LOCK2, D3DDDICB_LOCK2 structure [Display Devices], _D3DDDICB_LOCK2, d3dumddi/D3DDDICB_LOCK2, display.d3dddicb_lock2
f1_keywords:
 - "d3dumddi/D3DDDICB_LOCK2"
 - "D3DDDICB_LOCK2"
req.header: d3dumddi.h
req.include-header: D3dumddi.h
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
- d3dumddi.h
api_name:
- D3DDDICB_LOCK2
targetos: Windows
req.typenames: D3DDDICB_LOCK2
---

# _D3DDDICB_LOCK2 structure


## -description


<b>D3DDDICB_LOCK2</b> describes parameters for locking an allocation.


## -struct-fields




### -field hAllocation

[in] A driver specified <b>D3DKMT_HANDLE</b> to the allocation to lock.


### -field Flags

A set of flags to pass to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtlock2">Lock2</a> kernel function which will determine how the allocation is locked. See <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lock2flags">D3DDDICB_LOCK2FLAGS</a> for details.


### -field pData

[out] A CPU virtual address pointing a valid memory location pointing to the CPU backing store or the GPU frame buffer.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dukmdt/ns-d3dukmdt-_d3dddicb_lock2flags">D3DDDICB_LOCK2FLAGS</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtlock2">Lock2</a>
 

 

