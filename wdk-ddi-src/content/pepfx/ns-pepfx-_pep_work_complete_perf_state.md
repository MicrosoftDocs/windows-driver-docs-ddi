---
UID: NS:pepfx._PEP_WORK_COMPLETE_PERF_STATE
title: "_PEP_WORK_COMPLETE_PERF_STATE"
author: windows-driver-content
description: The PEP_WORK_COMPLETE_PERF_STATE structure describes the completion status of a previously requested update to the performance values assigned to a list of performance state (P-state) sets.
old-location: kernel\pep_work_complete_perf_state.htm
old-project: kernel
ms.assetid: B28BE626-5DF1-4B55-8D1A-04B1FF2245EA
ms.author: windowsdriverdev
ms.date: 3/28/2018
ms.keywords: "*PPEP_WORK_COMPLETE_PERF_STATE, PEP_WORK_COMPLETE_PERF_STATE, PEP_WORK_COMPLETE_PERF_STATE structure [Kernel-Mode Driver Architecture], PPEP_WORK_COMPLETE_PERF_STATE, PPEP_WORK_COMPLETE_PERF_STATE structure pointer [Kernel-Mode Driver Architecture], _PEP_WORK_COMPLETE_PERF_STATE, kernel.pep_work_complete_perf_state, pepfx/PEP_WORK_COMPLETE_PERF_STATE, pepfx/PPEP_WORK_COMPLETE_PERF_STATE"
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
-	PEP_WORK_COMPLETE_PERF_STATE
product: Windows
targetos: Windows
req.typenames: PEP_WORK_COMPLETE_PERF_STATE, *PPEP_WORK_COMPLETE_PERF_STATE
---

# _PEP_WORK_COMPLETE_PERF_STATE structure


## -description


The <b>PEP_WORK_COMPLETE_PERF_STATE</b> structure describes the completion status of a previously requested update to the performance values assigned to a list of performance state (P-state) sets.


## -struct-fields




### -field DeviceHandle

A handle that represents the registration of the device with the Windows <a href="https://msdn.microsoft.com/9F2D8ACD-44D5-46E0-9FC7-1B38B99450FF">power management framework</a> (PoFx). The PEP received this handle in a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a> notification.


### -field Component

[in] The index that identifies the component. This member is an index into the <b>Components</b> array in the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a> structure that the PEP previously supplied in response to the <b>PEP_DPM_REGISTER_DEVICE</b> notification for this device. If the <b>Components</b> array contains N elements, component indexes range from 0 to N–1.


### -field Succeeded

Whether the requested P-state changes successfully completed. Set to TRUE if the PEP successfully completed all P-state changes requested in a previous <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186852">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a> notification. Set to FALSE if the PEP was unable to perform all the requested P-state changes, in which case the P-states in the hardware were left unchanged.


## -remarks



The <b>CompletePerfState</b> member of the <a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a> structure is a <b>PEP_WORK_COMPLETE_PERF_STATE</b> structure. If PoFx sends a <a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186852">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a> notification to request performance level changes to one or more P-state sets, and the PEP chooses to handle this request asynchronously, the PEP uses a <b>PEP_WORK_COMPLETE_PERF_STATE</b> structure to describe the completion status of the request.




## -see-also




<a href="https://msdn.microsoft.com/library/windows/hardware/mt186713">PEP_DEVICE_REGISTER_V2</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186849">PEP_DPM_REGISTER_DEVICE</a>



<a href="https://msdn.microsoft.com/en-us/library/windows/hardware/mt186852">PEP_DPM_REQUEST_COMPONENT_PERF_STATE</a>



<a href="https://msdn.microsoft.com/library/windows/hardware/mt186864">PEP_WORK_INFORMATION</a>
 

 

