---
UID: NS:pep_x._PEP_PPM_QUERY_IDLE_STATES
title: _PEP_PPM_QUERY_IDLE_STATES (pep_x.h)
description: The PEP_PPM_QUERY_IDLE_STATES structure describes the idle states of a particular processor.
old-location: kernel\pep_ppm_query_idle_states.htm
tech.root: kernel
ms.assetid: 27B43684-6564-41A0-9F0D-D49F88D1F14D
ms.date: 04/30/2018
ms.keywords: "*PPEP_PPM_QUERY_IDLE_STATES, PEP_PPM_QUERY_IDLE_STATES, PEP_PPM_QUERY_IDLE_STATES structure [Kernel-Mode Driver Architecture], PPEP_PPM_QUERY_IDLE_STATES, PPEP_PPM_QUERY_IDLE_STATES structure pointer [Kernel-Mode Driver Architecture], _PEP_PPM_QUERY_IDLE_STATES, kernel.pep_ppm_query_idle_states, pep_x/PEP_PPM_QUERY_IDLE_STATES, pep_x/PPEP_PPM_QUERY_IDLE_STATES"
ms.topic: struct
f1_keywords:
 - "pep_x/PEP_PPM_QUERY_IDLE_STATES"
req.header: pep_x.h
req.include-header: Pepfx.h
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
- pep_x.h
api_name:
- PEP_PPM_QUERY_IDLE_STATES
product:
- Windows
targetos: Windows
req.typenames: PEP_PPM_QUERY_IDLE_STATES, *PPEP_PPM_QUERY_IDLE_STATES
---

# _PEP_PPM_QUERY_IDLE_STATES structure


## -description


The <b>PEP_PPM_QUERY_IDLE_STATES</b> structure describes the idle states of a particular processor.


## -struct-fields




### -field Count

[in] The number of elements in the <b>IdleStates</b> array. This member is set to the <b>IdleStateCount</b> value that the PEP previously supplied for this processor in response to the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a> notification.


### -field MaximumCoordinatedProcessors

[out] The maximum number of secondary processors that are subordinate to this processor for any transitions to idle states. A primary processor can enter the selected idle state only after the secondary processors have entered their corresponding idle states. The PEP must set the <b>MaximumCoordinatedProcessors</b> member to a number that is less than the total number of processors in the hardware platform.


### -field IdleStates

[in] The first element in an array of <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pep_x/ns-pep_x-_pep_processor_idle_state">PEP_PROCESSOR_IDLE_STATE</a> structures. Each array element describes one of the idle states of this processor. If the array contains more than one element, the additional elements immediately follow the end of the <b>PEP_PPM_QUERY_IDLE_STATES</b> structure. The number of array elements is specified by the <b>Count</b> member. The buffer that PoFx allocates to hold this structure is guaranteed to be large enough to contain the <b>PEP_PPM_QUERY_IDLE_STATES</b> structure plus any array elements that follow this structure. Each idle state is identified by its array index. If the array contains N elements, idle state indexes range from 0 to N–1.


## -remarks



This structure is used by the <a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pep_x/ns-pep_x-_pep_ppm_query_idle_states">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a> notification. The <b>Count</b> member of the structure contains an input value that PoFx supplies when this notification is sent. The other two members contain output values that the PEP writes to the structure in response to the notification.




## -see-also




<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pepfx/ns-pepfx-_pep_ppm_query_capabilities">PEP_NOTIFY_PPM_QUERY_CAPABILITIES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pep_x/ns-pep_x-_pep_ppm_query_idle_states">PEP_NOTIFY_PPM_QUERY_IDLE_STATES</a>



<a href="https://docs.microsoft.com/windows-hardware/drivers/ddi/content/pep_x/ns-pep_x-_pep_processor_idle_state">PEP_PROCESSOR_IDLE_STATE</a>
 

 

