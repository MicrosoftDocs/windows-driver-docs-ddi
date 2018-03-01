---
UID: NS:d3dkmddi._DXGKARG_PREEMPTCOMMAND
title: "_DXGKARG_PREEMPTCOMMAND"
author: windows-driver-content
description: The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the DxgkDdiSubmitCommand function previously submitted to the hardware command execution unit.
old-location: display\dxgkarg_preemptcommand.htm
old-project: display
ms.assetid: de8f8bee-44e9-4a6a-bb36-a43a66afe188
ms.author: windowsdriverdev
ms.date: 2/26/2018
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
req.irql: PASSIVE_LEVEL
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


The DXGKARG_PREEMPTCOMMAND structure describes a command that a display miniport driver must use to preempt a direct memory access (DMA) buffer that the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a> function previously submitted to the hardware command execution unit.


## -syntax


````
typedef struct _DXGKARG_PREEMPTCOMMAND {
  UINT                     PreemptionFenceId;
  UINT                     NodeOrdinal;
  UINT                     EngineOrdinal;
  DXGK_PREEMPTCOMMANDFLAGS Flags;
} DXGKARG_PREEMPTCOMMAND;
````


## -struct-fields




### -field PreemptionFenceId

[in] A unique identifier that the display miniport driver must patch into the fence command at the end of the DMA buffer to preempt the previously submitted DMA buffer. The display miniport driver uses the identifier in a call to the <a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a> function to inform the graphics processing unit (GPU) scheduler about the preemption at deferred-procedure-call (DPC) time.


### -field NodeOrdinal

[in] The index of the node for the preemption request. 


### -field EngineOrdinal

[in] The index of the engine for the preemption request.


### -field Flags

[in] A <a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_preemptcommandflags.md">DXGK_PREEMPTCOMMANDFLAGS</a> structure with a reserved member or a 32-bit value. No flags are currently defined for this structure.


## -see-also

<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_createdevice.md">DxgkDdiCreateDevice</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_submitcommand.md">DxgkDdiSubmitCommand</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_dpc.md">DxgkCbNotifyDpc</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkcb_notify_interrupt.md">DxgkCbNotifyInterrupt</a>



<a href="..\d3dkmddi\nc-d3dkmddi-dxgkddi_preemptcommand.md">DxgkDdiPreemptCommand</a>



<a href="..\d3dkmddi\ns-d3dkmddi-_dxgk_preemptcommandflags.md">DXGK_PREEMPTCOMMANDFLAGS</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [display\display]:%20DXGKARG_PREEMPTCOMMAND structure%20 RELEASE:%20(2/26/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

