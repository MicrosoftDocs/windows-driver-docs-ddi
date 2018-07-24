---
UID: NS:d3dkmdt._D3DKMDT_PREEMPTION_CAPS
title: "_D3DKMDT_PREEMPTION_CAPS"
author: windows-driver-content
description: Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports.
old-location: display\d3dkmdt_preemption_caps.htm
tech.root: display
ms.assetid: 52172edc-77a9-46b9-8382-c57c65b80b93
ms.author: windowsdriverdev
ms.date: 5/10/2018
ms.keywords: D3DKMDT_PREEMPTION_CAPS, D3DKMDT_PREEMPTION_CAPS structure [Display Devices], _D3DKMDT_PREEMPTION_CAPS, d3dkmdt/D3DKMDT_PREEMPTION_CAPS, display.d3dkmdt_preemption_caps
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
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
-	D3DKMDT_PREEMPTION_CAPS
product:
- Windows
targetos: Windows
req.typenames: D3DKMDT_PREEMPTION_CAPS
---

# _D3DKMDT_PREEMPTION_CAPS structure


## -description


Specifies the capabilities for the preemption of graphic processing unit (GPU) graphics requests that the display miniport driver supports.


## -struct-fields




### -field GraphicsPreemptionGranularity

A  <a href="https://msdn.microsoft.com/library/windows/hardware/hh439329">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a> value that specifies the level of graphics requests  that the driver can preempt for GPU graphics  operations.


### -field ComputePreemptionGranularity

A <a href="https://msdn.microsoft.com/library/windows/hardware/hh439326">D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY</a> value that specifies the level of graphics requests that the driver can preempt for GPU compute shader operations.


## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/hh439326">D3DKMDT_COMPUTE_PREEMPTION_GRANULARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/hh439329">D3DKMDT_GRAPHICS_PREEMPTION_GRANULARITY</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/ff561062">DXGK_DRIVERCAPS</a>
 

 

