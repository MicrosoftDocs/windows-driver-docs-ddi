---
UID: NC:pepfx.POFXCALLBACKUPDATEPLATFORMIDLESTATE
title: POFXCALLBACKUPDATEPLATFORMIDLESTATE (pepfx.h)
description: The UpdatePlatformIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state.
old-location: kernel\updateplatformidlestate.htm
tech.root: kernel
ms.assetid: A5E3C5DE-DD76-41CF-8A86-37F25A069E1C
ms.date: 04/30/2018
ms.keywords: POFXCALLBACKUPDATEPLATFORMIDLESTATE, UpdatePlatformIdleState, UpdatePlatformIdleState routine [Kernel-Mode Driver Architecture], kernel.updateplatformidlestate, pepfx/UpdatePlatformIdleState
f1_keywords:
 - "pepfx/UpdatePlatformIdleState"
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
- APIRef
- kbSyntax
api_type:
- UserDefined
api_location:
- pepfx.h
api_name:
- UpdatePlatformIdleState
product:
- Windows
targetos: Windows
req.typenames: 
---

# POFXCALLBACKUPDATEPLATFORMIDLESTATE callback function


## -description


The <b>UpdatePlatformIdleState</b> routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state.


## -parameters




### -param ProcessorHandle [in]

A POHANDLE value that represents the registration of the processor (as a device) with the Windows <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/index">power management framework</a> (PoFx). The PEP previously received this handle from PoFx during the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the processor had been registered with PoFx.


### -param PlatformState [in]

An index that identifies the platform idle state whose properties are to be updated. In response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification, the PEP specified the number of supported platform idle states. If the PEP specified N platform idle states, valid platform idle state indexes range from 0 to N-1. In response to a previous <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification, the PEP specified the properties of this platform idle state.


### -param Update [in]

A pointer to a <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_platform_idle_state_update">PEP_PLATFORM_IDLE_STATE_UPDATE</a> structure that contains the updated properties of the platform idle state.


## -returns



<b>UpdatePlatformIdleState</b> returns STATUS_SUCCESS if it successfully updates the properties of the platform idle state. Possible error return values include the following status codes.

<table>
<tr>
<th>Return value</th>
<th>Description</th>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NOT_SUPPORTED</dt>
</dl>
</td>
<td width="60%">
The version number in the <b>PEP_PLATFORM_IDLE_STATE_UPDATE</b> structure is not a supported value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>
</td>
<td width="60%">
The <b>UpdatePlatformIdleState</b> routine is not implemented for this processor.

</td>
</tr>
</table>
 




## -remarks



This routine is implemented by PoFx and is called by the PEP. The <b>UpdatePlatformIdleState</b> member of the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>UpdatePlatformIdleState</b> routine.

 The PEP must wait until after it has completed all <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notifications to call the <b>UpdatePlatformIdleState</b> routine.

The <b>UpdatePlatformIdleState</b> routine must be called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_register_crashdump_device">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_kernel_information_struct_v3">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_state">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_ppm_query_platform_states">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/pepfx/ns-pepfx-_pep_platform_idle_state_update">PEP_PLATFORM_IDLE_STATE_UPDATE</a>
 

 

