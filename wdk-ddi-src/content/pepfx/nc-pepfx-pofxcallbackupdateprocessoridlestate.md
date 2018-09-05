---
UID: NC:pepfx.POFXCALLBACKUPDATEPROCESSORIDLESTATE
title: POFXCALLBACKUPDATEPROCESSORIDLESTATE
author: windows-driver-content
description: The UpdateProcessorIdleState routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state.
old-location: kernel\updateprocessoridlestate.htm
tech.root: kernel
ms.assetid: 023A2637-A79A-4ADE-B54C-646CBDDF08B8
ms.author: windowsdriverdev
ms.date: 4/30/2018
ms.keywords: POFXCALLBACKUPDATEPROCESSORIDLESTATE, UpdateProcessorIdleState, UpdateProcessorIdleState routine [Kernel-Mode Driver Architecture], kernel.updateprocessoridlestate, pepfx/UpdateProcessorIdleState
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
-	UpdateProcessorIdleState
product:
- Windows
targetos: Windows
req.typenames: 
---

# POFXCALLBACKUPDATEPROCESSORIDLESTATE callback function


## -description


The <b>UpdateProcessorIdleState</b> routine is called by the platform extension plug-in (PEP) to update the properties of the specified processor idle state.


## -parameters




### -param ProcessorHandle [in]

A POHANDLE value that represents the registration of the processor (as a device) with the Windows <a href="https://msdn.microsoft.com/B08F8ABF-FD43-434C-A345-337FBB799D9B">power management framework</a> (PoFx). The PEP previously received this handle from PoFx during the <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification that informed the PEP that the processor had been registered with PoFx.


### -param ProcessorState [in]

An index that identifies the processor idle state whose properties are to be updated. In response to a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186824">PEP_NOTIFY_PPM_QUERY_IDLE_STATES_V2</a> notification, the PEP specified the number of supported processor idle states and the properties of these states. If the PEP specified N processor idle states, valid processor idle state indexes range from 0 to N-1.


### -param Update [in]

A pointer to a <a href="https://msdn.microsoft.com/library/windows/hardware/mt186835">PEP_PROCESSOR_IDLE_STATE_UPDATE</a> structure that contains the updated properties of the processor idle state.


## -returns



<b>UpdateProcessorIdleState</b> returns STATUS_SUCCESS if it successfully updates the properties of the processor idle state. Possible error return values include the following status codes.

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
The version number in the <b>PEP_PROCESSOR_IDLE_STATE_UPDATE</b> structure is not a supported value.

</td>
</tr>
<tr>
<td width="40%">
<dl>
<dt>STATUS_NOT_IMPLEMENTED</dt>
</dl>
</td>
<td width="60%">
The <b>UpdateProcessorIdleState</b> routine is not implemented for this processor.

</td>
</tr>
</table>
 




## -remarks



This routine is implemented by PoFx and is called by the PEP. The <b>UpdateProcessorIdleState</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a> structure is a pointer to an <b>UpdateProcessorIdleState</b> routine.

The <b>UpdateProcessorIdleState</b> routine must be called at IRQL = PASSIVE_LEVEL.




## -see-also




<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186747">PEP_KERNEL_INFORMATION_STRUCT_V3</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186835">PEP_PROCESSOR_IDLE_STATE_UPDATE</a>
 

 

