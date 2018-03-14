---
UID: NC:pepfx.POFXCALLBACKUPDATEPLATFORMIDLESTATE
title: POFXCALLBACKUPDATEPLATFORMIDLESTATE
author: windows-driver-content
description: The UpdatePlatformIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state.
old-location: kernel\updateplatformidlestate.htm
old-project: kernel
ms.assetid: A5E3C5DE-DD76-41CF-8A86-37F25A069E1C
ms.author: windowsdriverdev
ms.date: 3/1/2018
ms.keywords: POFXCALLBACKUPDATEPLATFORMIDLESTATE, UpdatePlatformIdleState, UpdatePlatformIdleState routine [Kernel-Mode Driver Architecture], kernel.updateplatformidlestate, pepfx/UpdatePlatformIdleState
ms.prod: windows-hardware
ms.technology: windows-devices
ms.topic: callback
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
-	UserDefined
api_location:
-	pepfx.h
api_name:
-	UpdatePlatformIdleState
product: Windows
targetos: Windows
req.typenames: VPCI_PNP_ID, *PVPCI_PNP_ID
---

# POFXCALLBACKUPDATEPLATFORMIDLESTATE callback


## -description


The <b>UpdatePlatformIdleState</b> routine is called by the platform extension plug-in (PEP) to update the properties of the specified platform idle state.


## -prototype


````
POFXCALLBACKUPDATEPLATFORMIDLESTATE UpdatePlatformIdleState;

NTSTATUS UpdatePlatformIdleState(
  _In_ POHANDLE                        ProcessorHandle,
  _In_ ULONG                           PlatformState,
  _In_ PPEP_PLATFORM_IDLE_STATE_UPDATE Update
)
{ ... }
````


## -parameters




### -param ProcessorHandle [in]

A POHANDLE value that represents the registration of the processor (as a device) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The PEP previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the processor had been registered with PoFx.


### -param PlatformState [in]

An index that identifies the platform idle state whose properties are to be updated. In response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a> notification, the PEP specified the number of supported platform idle states. If the PEP specified N platform idle states, valid platform idle state indexes range from 0 to Nâ€“-1. In response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notification, the PEP specified the properties of this platform idle state.


### -param Update [in]

A pointer to a <a href="..\pepfx\ns-pepfx-_pep_platform_idle_state_update.md">PEP_PLATFORM_IDLE_STATE_UPDATE</a> structure that contains the updated properties of the platform idle state.


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



This routine is implemented by PoFx and is called by the PEP. The <b>UpdatePlatformIdleState</b> member of the <a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>UpdatePlatformIdleState</b> routine.

 The PEP must wait until after it has completed all <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a> notifications to call the <b>UpdatePlatformIdleState</b> routine.

The <b>UpdatePlatformIdleState</b> routine must be called at IRQL = PASSIVE_LEVEL.




## -see-also

<a href="..\pepfx\ns-pepfx-_pep_kernel_information_struct_v3.md">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="..\pepfx\ns-pepfx-_pep_platform_idle_state_update.md">PEP_PLATFORM_IDLE_STATE_UPDATE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186827">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATES</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186826">PEP_NOTIFY_PPM_QUERY_PLATFORM_STATE</a>



 

 

<a href="mailto:wsddocfb@microsoft.com?subject=Documentation%20feedback [kernel\kernel]:%20POFXCALLBACKUPDATEPLATFORMIDLESTATE routine%20 RELEASE:%20(3/1/2018)&amp;body=%0A%0APRIVACY STATEMENT%0A%0AWe use your feedback to improve the documentation. We don't use your email address for any other purpose, and we'll remove your email address from our system after the issue that you're reporting is fixed. While we're working to fix this issue, we might send you an email message to ask for more info. Later, we might also send you an email message to let you know that we've addressed your feedback.%0A%0AFor more info about Microsoft's privacy policy, see http://privacy.microsoft.com/en-us/default.aspx." title="Send comments about this topic to Microsoft">Send comments about this topic to Microsoft</a>

