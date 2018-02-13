---
UID: NS:pepfx._PEP_PPM_QUERY_PLATFORM_STATE
title: "_PEP_PPM_QUERY_PLATFORM_STATE"
author: windows-driver-content
description: The PEP_PPM_QUERY_PLATFORM_STATE structure contains information about a platform idle state.
old-location: kernel\pep_ppm_query_platform_state.htm
old-project: kernel
ms.assetid: 767F7364-07E4-4B64-AEAE-EEAEEADA5DFE
ms.author: windowsdriverdev
ms.date: 1/4/2018
ms.keywords: PEP_PPM_QUERY_PLATFORM_STATE, pepfx/PPEP_PPM_QUERY_PLATFORM_STATE, kernel.pep_ppm_query_platform_state, _PEP_PPM_QUERY_PLATFORM_STATE, pepfx/PEP_PPM_QUERY_PLATFORM_STATE, PPEP_PPM_QUERY_PLATFORM_STATE structure pointer [Kernel-Mode Driver Architecture], *PPEP_PPM_QUERY_PLATFORM_STATE, PPEP_PPM_QUERY_PLATFORM_STATE, PEP_PPM_QUERY_PLATFORM_STATE structure [Kernel-Mode Driver Architecture]
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
-	PEP_PPM_QUERY_PLATFORM_STATE
product: Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_PLATFORM_STATE, *PPEP_PPM_QUERY_PLATFORM_STATE
---

# _PEP_PPM_QUERY_PLATFORM_STATE structure


## -description


The <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure contains information about a platform idle state.


## -syntax


````
typedef struct _PEP_PPM_QUERY_PLATFORM_STATE {
  ULONG                   StateIndex;
  PEP_PLATFORM_IDLE_STATE State;
} PEP_PPM_QUERY_PLATFORM_STATE, *PPEP_PPM_QUERY_PLATFORM_STATE;
````


## -struct-fields




### -field StateIndex

[in] The index of this platform idle state. If the hardware platform supports N platform idle states, the states are numbered 0 to N-1. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) previously sent a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification to the platform extension plug-in (PEP) to determine the number of supported platform idle states.


### -field State

[out] A <a href="..\pepfx\ns-pepfx-_pep_platform_idle_state.md">PEP_PLATFORM_IDLE_STATE</a> structure that describes the platform idle state.


## -remarks



This structure is used by the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification. The <b>StateIndex</b> member of the <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure contains an input value that is supplied by the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) when this notification is sent to the PEP. The <b>State</b> member contains an output value that the PEP writes to the structure in response to the notification.

The buffer that PoFx allocates to hold the <b>PEP_PPM_QUERY_PLATFORM_STATE</b> structure is guaranteed to be large enough to contain this structure plus any elements of the <b>State.DependencyArray</b> array that follow this structure.




## -see-also

<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="..\pepfx\ns-pepfx-_pep_platform_idle_state.md">PEP_PLATFORM_IDLE_STATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PPM_QUERY_PLATFORM_STATE structure%20 RELEASE:%20(1/4/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

