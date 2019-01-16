---
UID: NE:d3dkmdt._D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
title: "_D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY"
description: Specifies the capabilities for the preemption of graphic processing unit (GPU) compute shader operations that the display miniport driver supports.
old-location: display\d3dkmdt_compute_preemption_granularity.htm
tech.root: display
ms.assetid: d8ed5406-3b76-49a7-961c-0be737b1dda9
ms.date: 05/10/2018
ms.keywords: D3DKMDT_COMPUTE_PREEMPTION_DISPATCH_BOUNDARY, D3DKMDT_COMPUTE_PREEMPTION_DMA_BUFFER_BOUNDARY, D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY, D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY enumeration [Display Devices], D3DKMDT_COMPUTE_PREEMPTION_NONE, D3DKMDT_COMPUTE_PREEMPTION_SHADER_BOUNDARY, D3DKMDT_COMPUTE_PREEMPTION_THREAD_BOUNDARY, D3DKMDT_COMPUTE_PREEMPTION_THREAD_GROUP_BOUNDARY, _D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_DISPATCH_BOUNDARY, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_DMA_BUFFER_BOUNDARY, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_NONE, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_SHADER_BOUNDARY, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_THREAD_BOUNDARY, d3dkmdt/D3DKMDT_COMPUTE_PREEMPTION_THREAD_GROUP_BOUNDARY, display.d3dkmdt_compute_preemption_granularity
ms.topic: enum
req.header: d3dkmdt.h
req.include-header: D3dkmdt.h
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
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	D3dkmdt.h
api_name:
-	D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY
---

# _D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY enumeration


## -description


Specifies the capabilities for the preemption of graphic processing unit (GPU) compute shader operations that the display miniport driver supports.


## -enum-fields




### -field D3DKMDT_COMPUTE_PREEMPTION_NONE

The driver does not support the preemption of GPU compute shader operations.

<div class="alert"><b>Note</b>  This value also specifies that the driver cannot stop currently running DMA buffers of a specified type and cannot prevent all pending DMA buffers in the hardware queue from running.</div>
<div> </div>

### -field D3DKMDT_COMPUTE_PREEMPTION_DMA_BUFFER_BOUNDARY

The driver cannot stop currently running DMA buffers of a specified type but can prevent all pending DMA buffers in the hardware queue from running.


### -field D3DKMDT_COMPUTE_PREEMPTION_DISPATCH_BOUNDARY

The driver cannot stop currently executing compute shader commands that were dispatched from a thread group but can prevent all pending commands from being dispatched.


### -field D3DKMDT_COMPUTE_PREEMPTION_THREAD_GROUP_BOUNDARY

The driver cannot stop currently executing compute shader commands that were dispatched from a thread group but can prevent a thread group from dispatching other commands.


### -field D3DKMDT_COMPUTE_PREEMPTION_THREAD_BOUNDARY

The driver cannot stop currently executing compute shader commands that were dispatched from a thread in a thread group but can prevent a thread from dispatching other commands.


### -field D3DKMDT_COMPUTE_PREEMPTION_SHADER_BOUNDARY

The driver cannot stop currently running shader commands of a specified type but can prevent all shader commands in the hardware queue from running.


## -remarks



Starting with Windows 8, display miniport drivers need to specify the level of preemption granularity supported by the GPU when executing compute shader operations. Because  engines on the same adapter may potentially support different preemption levels, the driver should report the coarsest granularity among all engines capable of executing a particular type of compute shader requests. 

For example, if one engine supports the preemption of primitive level graphics requests, and another engine supports the preemption of triangle level graphics requests, the driver should report primitive level graphics preemption capability for that adapter.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439329">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439334">D3DKMDT_PREEMPTION_CAPS</a>
 

 

