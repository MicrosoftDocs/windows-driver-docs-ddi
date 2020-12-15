---
UID: NS:d3dukmdt._D3DDDICB_DESTROYALLOCATION2FLAGS
title: _D3DDDICB_DESTROYALLOCATION2FLAGS (d3dukmdt.h)
description: The D3DDDICB_DESTROYALLOCATION2FLAGS structure is used with the D3DKMT_DESTROYALLOCATION2 structure to describe parameters for releasing allocations with D3DKMTDestroyAllocation2.D3DDDICB_DESTROYALLOCATION2FLAGS structure is used with the D3DKMT_DESTROYALLOCATION2 structure to describe parameters for releasing allocations with D3DKMTDestroyAllocation2.
old-location: display\d3dddicb_destroyallocation2flags.htm
tech.root: display
ms.date: 05/10/2018
keywords: ["D3DDDICB_DESTROYALLOCATION2FLAGS structure"]
ms.keywords: D3DDDICB_DESTROYALLOCATION2FLAGS, D3DDDICB_DESTROYALLOCATION2FLAGS structure [Display Devices], _D3DDDICB_DESTROYALLOCATION2FLAGS, d3dukmdt/D3DDDICB_DESTROYALLOCATION2FLAGS, display.d3dddicb_destroyallocation2flags
req.header: d3dukmdt.h
req.include-header: D3dumddi.h, D3dkmddi.h
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
targetos: Windows
req.typenames: D3DDDICB_DESTROYALLOCATION2FLAGS
f1_keywords:
 - _D3DDDICB_DESTROYALLOCATION2FLAGS
 - d3dukmdt/_D3DDDICB_DESTROYALLOCATION2FLAGS
 - D3DDDICB_DESTROYALLOCATION2FLAGS
 - d3dukmdt/D3DDDICB_DESTROYALLOCATION2FLAGS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dukmdt.h
api_name:
 - D3DDDICB_DESTROYALLOCATION2FLAGS
---

# _D3DDDICB_DESTROYALLOCATION2FLAGS structure


## -description

The <b>D3DDDICB_DESTROYALLOCATION2FLAGS</b> structure is used with the <a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroyallocation2">D3DKMT_DESTROYALLOCATION2</a> structure to describe parameters for releasing allocations with <a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroyallocation2">D3DKMTDestroyAllocation2</a>.

## -struct-fields

### -field AssumeNotInUse

|Value|Meaning|
|--- |--- |
|FALSE|Instructs the video memory manager to assume that commands queued prior to the destruction request may attempt to access the allocation being destroyed and defers the destruction operation until the queued commands finish.|
|TRUE|Instructs the video memory manager to ignore pending commands on the owner device and destroy the allocations immediately.|

### -field SynchronousDestroy

|Value|Meaning|
|--- |--- |
|FALSE|Instructs the DirectX graphics kernel that the call may return prior to the underlying surface memory being fully reclaimed by the operating system.|
|TRUE|Instructs the DirectX graphics kernel to wait until surface memory is reclaimed by the operating system.|

### -field Reserved

This member is reserved and should be set to zero.

### -field SystemUseOnly

This member is reserved and should not be used by the user mode driver.

### -field Value

The consolidated value of the fields in the structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmthk/nf-d3dkmthk-d3dkmtdestroyallocation2">D3DKMTDestroyAllocation2</a>



<a href="/windows-hardware/drivers/ddi/d3dkmthk/ns-d3dkmthk-_d3dkmt_destroyallocation2">D3DKMT_DESTROYALLOCATION2</a>
