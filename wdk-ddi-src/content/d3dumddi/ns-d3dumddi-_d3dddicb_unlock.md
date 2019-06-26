---
UID: NS:d3dumddi._D3DDDICB_UNLOCK
title: _D3DDDICB_UNLOCK (d3dumddi.h)
description: The D3DDDICB_UNLOCK structure describes allocations to unlock.
old-location: display\d3dddicb_unlock.htm
tech.root: display
ms.assetid: 1e0e6313-1dfa-4b68-8f58-bfa79f3124d6
ms.date: 05/10/2018
ms.keywords: D3DDDICB_UNLOCK, D3DDDICB_UNLOCK structure [Display Devices], D3D_param_Structs_91515cd5-00b4-4ad6-a8a5-ff216ddec171.xml, _D3DDDICB_UNLOCK, d3dumddi/D3DDDICB_UNLOCK, display.d3dddicb_unlock
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Available in Windows Vista and later versions of the Windows operating systems.
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
topic_type:
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- d3dumddi.h
api_name:
- D3DDDICB_UNLOCK
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_UNLOCK
---

# _D3DDDICB_UNLOCK structure


## -description


The D3DDDICB_UNLOCK structure describes allocations to unlock. 


## -struct-fields




### -field NumAllocations

[in] The number of allocations in the array that is specified by <b>phAllocations</b>. 


### -field phAllocations

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations. The Microsoft Direct3D runtime's <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a> function returns these handles. Therefore, the user-mode display driver uses these handles to unlock the allocations.


## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_allocatecb">pfnAllocateCb</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/d3dumddi/nc-d3dumddi-pfnd3dddi_unlockcb">pfnUnlockCb</a>
 

 

