---
UID: NS:pepfx._PEP_PPM_TEST_IDLE_STATE
title: "_PEP_PPM_TEST_IDLE_STATE"
author: windows-driver-content
description: The PEP_PPM_TEST_IDLE_STATE structure contains information about whether the processor can immediately enter a processor idle state.
old-location: kernel\pep_ppm_test_idle_state.htm
tech.root: kernel
ms.assetid: 2B465848-6564-404F-8F5B-E761866278C5
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: "*PPEP_PPM_TEST_IDLE_STATE, PEP_PPM_TEST_IDLE_STATE, PEP_PPM_TEST_IDLE_STATE structure [Kernel-Mode Driver Architecture], PPEP_PPM_TEST_IDLE_STATE, PPEP_PPM_TEST_IDLE_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_TEST_IDLE_STATE, kernel.pep_ppm_test_idle_state, pepfx/PEP_PPM_TEST_IDLE_STATE, pepfx/PPEP_PPM_TEST_IDLE_STATE"
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
-	PEP_PPM_TEST_IDLE_STATE
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_TEST_IDLE_STATE, *PPEP_PPM_TEST_IDLE_STATE
---

# _PEP_PPM_TEST_IDLE_STATE structure


## -description


The <b>PEP_PPM_TEST_IDLE_STATE</b> structure contains information about whether the processor can immediately enter a processor idle state.


## -struct-fields




### -field ProcessorState

(input) The index of the processor idle state that is to be entered. The platform extension plug-in (PEP) previously specified the supported processor idle states in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1.


### -field PlatformState

[in] The index of the platform idle state that the hardware platform will enter when the processor enters the processor idle state specified by <b>ProcessorState</b>. The PEP previously specified the supported platform idle states in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If no change in platform idle state will occur, this member will contain the value <b>PEP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).


### -field VetoReason

[out] The nonzero index value that identifies reason the PEP needs to veto this idle state transition, or <b>PEP_IDLE_VETO_NONE</b> (0) if the PEP is prepared to immediately make this transition. If the PEP supports N veto reasons, valid veto reason indexes range from 1 to N. The PEP previously specified the number of supported veto reasons in response to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a> notification.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186831">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The PEP writes an output value to the <b>VetoReason</b> member of this structure.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186829">PEP_NOTIFY_PPM_QUERY_VETO_REASONS</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186831">PEP_NOTIFY_PPM_TEST_IDLE_STATE</a>
 

 

