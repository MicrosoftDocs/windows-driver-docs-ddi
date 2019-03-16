---
UID: NS:d3dumddi._D3DDDICB_RECLAIMALLOCATIONS
title: _D3DDDICB_RECLAIMALLOCATIONS (d3dumddi.h)
description: Describes video memory resources that are to be reclaimed and that the user-mode display driver previously offered for reuse. Used with the pfnReclaimAllocationsCb function.
old-location: display\d3dddicb_reclaimallocations.htm
tech.root: display
ms.assetid: 61c8fdbf-b003-4caa-af13-ba6f1e22400c
ms.date: 05/10/2018
ms.keywords: D3DDDICB_RECLAIMALLOCATIONS, D3DDDICB_RECLAIMALLOCATIONS structure [Display Devices], _D3DDDICB_RECLAIMALLOCATIONS, d3dumddi/D3DDDICB_RECLAIMALLOCATIONS, display.d3dddicb_reclaimallocations
ms.topic: struct
req.header: d3dumddi.h
req.include-header: D3dumddi.h
req.target-type: Windows
req.target-min-winverclnt: Windows 8
req.target-min-winversvr: Windows Server 2012
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
- D3dumddi.h
api_name:
- D3DDDICB_RECLAIMALLOCATIONS
product:
- Windows
targetos: Windows
req.typenames: D3DDDICB_RECLAIMALLOCATIONS
---

# _D3DDDICB_RECLAIMALLOCATIONS structure


## -description


Describes video memory resources that are to be reclaimed and that the user-mode display driver  previously offered  for reuse. Used with the  <a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a> function.


## -struct-fields




### -field pResources

[in] A pointer to an array of handles to the resources that are to be reclaimed.

If <b>pResources</b> is not <b>NULL</b>, the <b>HandleList</b> member must be <b>NULL</b>.

<div class="alert"><b>Note</b>  If resources were created with the <b>D3D10_DDI_BIND_PRESENT</b> flag value set in <i>pCreateResource</i>-&gt;<b>BindFlags</b>, the driver must not use the <b>pResources</b> member to reclaim by resource handles. Instead, the driver must reclaim the resources by using allocation handles specified by <b>HandleList</b>.</div>
<div> </div>

### -field HandleList

[in] An array of D3DKMT_HANDLE data types that represent kernel-mode handles to the allocations that are to be reclaimed.

If <b>HandleList</b> is not <b>NULL</b>, the <b>pResources</b> member must be <b>NULL</b>.


### -field pDiscarded

[out] An  array of Boolean values that specify whether each resource or allocation was discarded.

Each Boolean value in this array corresponds to a resource at the same index location in the arrays pointed to by <b>pResources</b> or   <b>HandleList.</b>

The DirectX graphics kernel subsystem sets each Boolean value to <b>TRUE</b> if the correponding resource was discarded, or to <b>FALSE</b> if not.

The value of <b>pDiscarded</b> can be <b>NULL</b>. If the driver sets it to <b>NULL</b>, the content of the resource or allocation can be assumed to be lost. If the driver does not need the content of the resource or allocation, setting <b>pDiscarded</b> to <b>NULL</b> might improve performance.


### -field NumAllocations

[in] The number of items in the <b>pResources</b>, <b>HandleList</b>, or  <b>pDiscarded</b> members, whichever is not <b>NULL</b>.


## -see-also




<a href="https://msdn.microsoft.com/2dff9d2e-c497-422f-824b-a7101904fd67">CreateResource(D3D11)</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff541697">D3D10DDIARG_CREATERESOURCE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh451695">pfnReclaimAllocationsCb</a>
 

 

