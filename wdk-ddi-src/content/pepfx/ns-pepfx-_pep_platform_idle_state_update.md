---
UID: NS:pepfx._PEP_PLATFORM_IDLE_STATE_UPDATE
title: "_PEP_PLATFORM_IDLE_STATE_UPDATE"
author: windows-driver-content
description: The PEP_PLATFORM_IDLE_STATE_UPDATE structure contains the updated properties of a platform idle state.
old-location: kernel\pep_platform_idle_state_update.htm
old-project: kernel
ms.assetid: 488DA7B7-FB11-4AEF-902C-E461A281DF68
ms.author: windowsdriverdev
ms.date: 2/24/2018
ms.keywords: "*PPEP_PLATFORM_IDLE_STATE_UPDATE, PEP_PLATFORM_IDLE_STATE_UPDATE, PEP_PLATFORM_IDLE_STATE_UPDATE structure [Kernel-Mode Driver Architecture], PPEP_PLATFORM_IDLE_STATE_UPDATE, PPEP_PLATFORM_IDLE_STATE_UPDATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PLATFORM_IDLE_STATE_UPDATE, kernel.pep_platform_idle_state_update, pepfx/PEP_PLATFORM_IDLE_STATE_UPDATE, pepfx/PPEP_PLATFORM_IDLE_STATE_UPDATE"
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
req.irql: PASSIVE_LEVEL
topic_type:
-	APIRef
-	kbSyntax
api_type:
-	HeaderDef
api_location:
-	pepfx.h
api_name:
-	PEP_PLATFORM_IDLE_STATE_UPDATE
product: Windows
targetos: Windows
req.typenames: PEP_PLATFORM_IDLE_STATE_UPDATE, *PPEP_PLATFORM_IDLE_STATE_UPDATE
---

# _PEP_PLATFORM_IDLE_STATE_UPDATE structure


## -description


The <b>PEP_PLATFORM_IDLE_STATE_UPDATE</b> structure contains the updated properties of a platform idle state.


## -syntax


````
typedef struct _PEP_PLATFORM_IDLE_STATE_UPDATE {
  ULONG Version;
  ULONG Latency;
  ULONG BreakEvenDuration;
} PEP_PLATFORM_IDLE_STATE_UPDATE, *PPEP_PLATFORM_IDLE_STATE_UPDATE;
````


## -struct-fields




### -field Version

The current version number of this structure. Set this member to PEP_PLATFORM_IDLE_STATE_UPDATE_VERSION.


### -field Latency

The worst-case latency, in 100-nanosecond units, for the platform to wake from this idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. The Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx) uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.


## -remarks



The <i>Update</i> parameter of the <a href="..\pepfx\nc-pepfx-pofxcallbackupdateplatformidlestate.md">UpdatePlatformIdleState</a> routine is a pointer to a <b>PEP_PLATFORM_IDLE_STATE_UPDATE</b> structure.




## -see-also

<a href="..\pepfx\nc-pepfx-pofxcallbackupdateplatformidlestate.md">UpdatePlatformIdleState</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20PEP_PLATFORM_IDLE_STATE_UPDATE structure%20 RELEASE:%20(2/24/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

