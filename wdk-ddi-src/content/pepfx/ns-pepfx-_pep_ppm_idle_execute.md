---
UID: NS:pepfx._PEP_PPM_IDLE_EXECUTE
title: "_PEP_PPM_IDLE_EXECUTE"
author: windows-driver-content
description: The PEP_PPM_IDLE_EXECUTE structure specifies the idle state that the processor is to enter.
old-location: kernel\pep_ppm_idle_execute.htm
tech.root: kernel
ms.assetid: 88BE0C4E-0607-48D6-B0E1-7B35BFD70AD4
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_PPM_IDLE_EXECUTE, PEP_PPM_IDLE_EXECUTE, PEP_PPM_IDLE_EXECUTE structure [Kernel-Mode Driver Architecture], PPEP_PPM_IDLE_EXECUTE, PPEP_PPM_IDLE_EXECUTE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_IDLE_EXECUTE, kernel.pep_ppm_idle_execute, pepfx/PEP_PPM_IDLE_EXECUTE, pepfx/PPEP_PPM_IDLE_EXECUTE"
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: Pep_x.h
req.target-type: Windows
req.target-min-winverclnt: Supported starting with Windows 10.
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
-	pepfx.h
api_name:
-	PEP_PPM_IDLE_EXECUTE
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_IDLE_EXECUTE, *PPEP_PPM_IDLE_EXECUTE
---

# _PEP_PPM_IDLE_EXECUTE structure


## -description


The <b>PEP_PPM_IDLE_EXECUTE</b> structure specifies the idle state that the processor is to enter.


## -struct-fields




### -field Status

[out] An <b>NTSTATUS</b> value that indicates whether the processor idle state transition was successful. The platform extension plug-in (PEP) sets this member to <b>STATUS_SUCCESSFUL</b> if the transition succeeded. Otherwise, this member is set to an appropriate error status code.


### -field ProcessorState

[in] The index of the processor idle state that the processor is to enter. The PEP previously specified the supported processor idle states in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1.


### -field PlatformState

[in] The index of the platform idle state that the hardware platform will enter when the processor enters the processor idle state specified by <b>ProcessorState</b>. The PEP previously specified the supported platform idle states in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If no change in platform idle state will occur, this member will contain the value P<b>EP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186807">PEP_NOTIFY_PPM_IDLE_EXECUTE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The <b>Status</b> member contains an output value that the PEP writes to this member.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186807">PEP_NOTIFY_PPM_IDLE_EXECUTE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt629121">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>
 

 

