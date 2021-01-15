---
UID: NS:d3dkmddi._DXGKARG_PREEMPTCOMMAND
title: _DXGKARG_PREEMPTCOMMAND (d3dkmddi.h)
description: The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the DxgkDdiSubmitCommand function previously submitted to the hardware command execution unit.
old-location: display\dxgkarg_preemptcommand.htm
ms.date: 05/10/2018
keywords: ["DXGKARG_PREEMPTCOMMAND structure"]
ms.keywords: DXGKARG_PREEMPTCOMMAND, DXGKARG_PREEMPTCOMMAND structure [Display Devices], DmStructs_2564ca47-8304-4a95-a408-2e5ccca7353d.xml, _DXGKARG_PREEMPTCOMMAND, d3dkmddi/DXGKARG_PREEMPTCOMMAND, display.dxgkarg_preemptcommand
req.header: d3dkmddi.h
req.include-header: D3dkmddi.h
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
targetos: Windows
tech.root: display
req.typenames: DXGKARG_PREEMPTCOMMAND
f1_keywords:
 - _DXGKARG_PREEMPTCOMMAND
 - d3dkmddi/_DXGKARG_PREEMPTCOMMAND
 - DXGKARG_PREEMPTCOMMAND
 - d3dkmddi/DXGKARG_PREEMPTCOMMAND
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - d3dkmddi.h
api_name:
 - _DXGKARG_PREEMPTCOMMAND
 - DXGKARG_PREEMPTCOMMAND
---

# _DXGKARG_PREEMPTCOMMAND structure


## -description

The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a> function previously submitted to the hardware command execution unit.

## -struct-fields

### -field PreemptionFenceId

[in] A unique identifier that the display miniport driver must patch into the fence command at the end of the DMA buffer to preempt the previously submitted DMA buffer. The display miniport driver uses the identifier in a call to the <a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a> function to inform the graphics processing unit (GPU) scheduler about the preemption at deferred-procedure-call (DPC) time.

### -field NodeOrdinal

[in] The index of the node for the preemption request.

### -field EngineOrdinal

[in] The index of the engine for the preemption request.

### -field Flags

[in] A <a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_preemptcommandflags">DXGK_PREEMPTCOMMANDFLAGS</a> structure with a reserved member or a 32-bit value. No flags are currently defined for this structure.

## -see-also

<a href="/windows-hardware/drivers/ddi/d3dkmddi/ns-d3dkmddi-_dxgk_preemptcommandflags">DXGK_PREEMPTCOMMANDFLAGS</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_dpc">DxgkCbNotifyDpc</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkcb_notify_interrupt">DxgkCbNotifyInterrupt</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_createdevice">DxgkDdiCreateDevice</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_preemptcommand">DxgkDdiPreemptCommand</a>



<a href="/windows-hardware/drivers/ddi/d3dkmddi/nc-d3dkmddi-dxgkddi_submitcommand">DxgkDdiSubmitCommand</a>

