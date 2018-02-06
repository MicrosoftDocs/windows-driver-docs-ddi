---
UID: NS:pepfx._PEP_PPM_IDLE_COMPLETE
title: "_PEP_PPM_IDLE_COMPLETE"
author: windows-driver-content
description: The PEP_PPM_IDLE_COMPLETE structure describe the idle states from which the processor and hardware platform are waking.
old-location: kernel\pep_ppm_idle_complete.htm
old-project: kernel
ms.assetid: F44C7FCC-0693-4F43-BF23-7160B67EDD3D
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PPEP_PPM_IDLE_COMPLETE structure pointer [Kernel-Mode Driver Architecture], kernel.pep_ppm_idle_complete, _PEP_PPM_IDLE_COMPLETE, pepfx/PPEP_PPM_IDLE_COMPLETE, pepfx/PEP_PPM_IDLE_COMPLETE, PEP_PPM_IDLE_COMPLETE, *PPEP_PPM_IDLE_COMPLETE, PPEP_PPM_IDLE_COMPLETE, PEP_PPM_IDLE_COMPLETE structure [Kernel-Mode Driver Architecture]
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: struct
req.header: pepfx.h
req.include-header: 
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
req.irql: PASSIVE_LEVEL
topictype:
-	APIRef
-	kbSyntax
apitype:
-	HeaderDef
apilocation:
-	pepfx.h
apiname:
-	PEP_PPM_IDLE_COMPLETE
product: Windows
targetos: Windows
req.typenames: "*PPEP_PPM_IDLE_COMPLETE, PEP_PPM_IDLE_COMPLETE"
---

# _PEP_PPM_IDLE_COMPLETE structure


## -description


The <b>PEP_PPM_IDLE_COMPLETE</b> structure describe the idle states from which the processor and hardware platform are waking.


## -syntax


````
typedef struct _PEP_PPM_IDLE_COMPLETE {
  ULONG ProcessorState;
  ULONG PlatformState;
} PEP_PPM_IDLE_COMPLETE, *PPEP_PPM_IDLE_COMPLETE;
````


## -struct-fields




### -field ProcessorState

[in] An index that identifies the idle state from which the processor is waking. The platform extension plug-in (PEP) previously specified the supported processor idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification. If the PEP specified N processor idle states, valid processor-idle-state indexes range from 0 to N-1. When the hypervisor is enabled and the platform wakes from an idle state, this member is set to <b>PEP_PROCESSOR_IDLE_STATE_UNKNOWN</b> (0xffffffff). For more information, see <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186803">PEP_NOTIFY_PPM_IDLE_COMPLETE</a>.


### -field PlatformState

[in] An index that identifies the idle state from which the platform is waking. The PEP previously specified the supported platform idle states in response to a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification. If the PEP specified M platform idle states, valid platform-idle-state indexes range from 0 to M-1. If the transition from the processor idle state does not involve a transition from an platform idle state, this member will contain the value <b>PEP_PLATFORM_IDLE_STATE_NONE</b> (0xffffffff).


## -remarks


This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186803">PEP_NOTIFY_PPM_IDLE_COMPLETE</a> notification. The <b>ProcessorState</b> and <b>PlatformState</b> members contain input values that are supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP.



## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186803">PEP_NOTIFY_PPM_IDLE_COMPLETE</a>

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a>

 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_IDLE_COMPLETE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

