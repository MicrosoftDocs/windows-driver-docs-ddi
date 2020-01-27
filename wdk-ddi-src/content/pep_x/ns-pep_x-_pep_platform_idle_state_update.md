---
UID: NS:pep_x._PEP_PLATFORM_IDLE_STATE_UPDATE
title: _PEP_PLATFORM_IDLE_STATE_UPDATE (pep_x.h)
description: The PEP_PLATFORM_IDLE_STATE_UPDATE structure contains the updated properties of a platform idle state.
old-location: kernel\pep_platform_idle_state_update.htm
tech.root: kernel
ms.assetid: 488DA7B7-FB11-4AEF-902C-E461A281DF68
ms.date: 04/30/2018
ms.keywords: "*PPEP_PLATFORM_IDLE_STATE_UPDATE, PEP_PLATFORM_IDLE_STATE_UPDATE, PEP_PLATFORM_IDLE_STATE_UPDATE structure [Kernel-Mode Driver Architecture], PPEP_PLATFORM_IDLE_STATE_UPDATE, PPEP_PLATFORM_IDLE_STATE_UPDATE structure pointer [Kernel-Mode Driver Architecture], _PEP_PLATFORM_IDLE_STATE_UPDATE, kernel.pep_platform_idle_state_update, pepfx/PEP_PLATFORM_IDLE_STATE_UPDATE, pepfx/PPEP_PLATFORM_IDLE_STATE_UPDATE"
f1_keywords:
 - "pep_x/PEP_PLATFORM_IDLE_STATE_UPDATE"
req.header: pep_x.h
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
- APIRef
- kbSyntax
api_type:
- HeaderDef
api_location:
- pepfx.h
api_name:
- PEP_PLATFORM_IDLE_STATE_UPDATE
product:
- Windows
targetos: Windows
req.typenames: PEP_PLATFORM_IDLE_STATE_UPDATE, *PPEP_PLATFORM_IDLE_STATE_UPDATE
---

# _PEP_PLATFORM_IDLE_STATE_UPDATE structure


## -description


The <b>PEP_PLATFORM_IDLE_STATE_UPDATE</b> structure contains the updated properties of a platform idle state.


## -struct-fields




### -field Version

The current version number of this structure. Set this member to PEP_PLATFORM_IDLE_STATE_UPDATE_VERSION.


### -field Latency

The worst-case latency, in 100-nanosecond units, for the platform to wake from this idle state in response to a wake event.


### -field BreakEvenDuration

The minimum amount of time, specified in 100-nanosecond units, that the platform must spend in this idle state to make a transition to this state worthwhile. The Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx) uses this member value as a hint to avoid switching the platform to an idle state unless the platform is likely to remain in this state for at least the amount of time specified by <b>BreakEvenDuration</b>.


## -remarks



The <i>Update</i> parameter of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateplatformidlestate">UpdatePlatformIdleState</a> routine is a pointer to a <b>PEP_PLATFORM_IDLE_STATE_UPDATE</b> structure.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/nc-pepfx-pofxcallbackupdateplatformidlestate">UpdatePlatformIdleState</a>
 

 

