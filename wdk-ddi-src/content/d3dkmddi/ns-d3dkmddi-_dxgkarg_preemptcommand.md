---
UID: NS:d3dkmddi._DXGKARG_PREEMPTCOMMAND
title: "_DXGKARG_PREEMPTCOMMAND"
author: windows-driver-content
description: The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the DxgkDdiSubmitCommand function previously submitted to the hardware command execution unit.
old-location: display\dxgkarg_preemptcommand.htm
old-project: display
ms.assetid: de8f8bee-44e9-4a6a-bb36-a43a66afe188
ms.author: windowsdriverdev
ms.date: 4/16/2018
ms.keywords: DXGKARG_PREEMPTCOMMAND, DXGKARG_PREEMPTCOMMAND structure [Display Devices], DmStructs_2564ca47-8304-4a95-a408-2e5ccca7353d.xml, _DXGKARG_PREEMPTCOMMAND, d3dkmddi/DXGKARG_PREEMPTCOMMAND, display.dxgkarg_preemptcommand
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	d3dkmddi.h
api_name:
-	DXGKARG_PREEMPTCOMMAND
product: Windows
targetos: Windows
req.typenames: DXGKARG_PREEMPTCOMMAND
---

# _DXGKARG_PREEMPTCOMMAND structure


## -description


The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the <a href="https://msdn.microsoft.com/de1925ab-e444-4cf6-acd9-8fdab26afcec">DxgkDdiSubmitCommand</a> function previously submitted to the hardware command execution unit.


## -struct-fields




### -field PreemptionFenceId

[in] A unique identifier that the display miniport driver must patch into the fence command at the end of the DMA buffer to preempt the previously submitted DMA buffer. The display miniport driver uses the identifier in a call to the <a href="https://msdn.microsoft.com/3df3f7d4-3721-46f5-b9e3-19bd3d870292">DxgkCbNotifyDpc</a> function to inform the graphics processing unit (GPU) scheduler about the preemption at deferred-procedure-call (DPC) time.


### -field NodeOrdinal

[in] The index of the node for the preemption request. 


### -field EngineOrdinal

[in] The index of the engine for the preemption request.


### -field Flags

[in] A <a href="https://msdn.microsoft.com/library/windows/hardware/ff561997">DXGK_PREEMPTCOMMANDFLAGS</a> structure with a reserved member or a 32-bit value. No flags are currently defined for this structure.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/ff561997">DXGK_PREEMPTCOMMANDFLAGS</a>



<a href="https://msdn.microsoft.com/3df3f7d4-3721-46f5-b9e3-19bd3d870292">DxgkCbNotifyDpc</a>



<a href="https://msdn.microsoft.com/7968d26d-0195-463d-8954-e7ebef4f9dea">DxgkCbNotifyInterrupt</a>



<a href="https://msdn.microsoft.com/a7027735-0ec4-4fad-81fb-1c3aca4ebf2d">DxgkDdiCreateDevice</a>



<a href="https://msdn.microsoft.com/8cea02d4-f25e-4ff4-8c9e-aa360a764c4b">DxgkDdiPreemptCommand</a>



<a href="https://msdn.microsoft.com/de1925ab-e444-4cf6-acd9-8fdab26afcec">DxgkDdiSubmitCommand</a>
 

 

