---
UID: NC:wdm.GET_D3COLD_LAST_TRANSITION_STATUS
title: GET_D3COLD_LAST_TRANSITION_STATUS (wdm.h)
description: The GetLastTransitionStatus routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate.
old-location: kernel\getlasttransitionstatus.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["GET_D3COLD_LAST_TRANSITION_STATUS callback function"]
ms.keywords: GET_D3COLD_LAST_TRANSITION_STATUS, GetLastTransitionStatus, GetLastTransitionStatus routine [Kernel-Mode Driver Architecture], kernel.getlasttransitionstatus, wdm/GetLastTransitionStatus
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Desktop
req.target-min-winverclnt: Available starting with Windows 8.
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
targetos: Windows
req.typenames: 
f1_keywords:
 - GET_D3COLD_LAST_TRANSITION_STATUS
 - wdm/GET_D3COLD_LAST_TRANSITION_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - UserDefined
api_location:
 - Wdm.h
api_name:
 - GET_D3COLD_LAST_TRANSITION_STATUS
---

# GET_D3COLD_LAST_TRANSITION_STATUS callback function


## -description

The <i>GetLastTransitionStatus</i> routine enables the driver for a device to query whether the most recent transition to the D3hot substate was followed by a transition to the D3cold substate.

## -parameters

### -param Context 

[in, optional]
A pointer to interface-specific context information. The caller sets this parameter to the value of the <b>Context</b> member of the <a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_d3cold_support_interface">D3COLD_SUPPORT_INTERFACE</a> structure for the interface.

### -param LastTransitionStatus 

[out]
A pointer to a variable into which the routine writes one of the following <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_d3cold_last_transition_status">D3COLD_LAST_TRANSITION_STATUS</a> enumeration values:

<ul>
<li><b>LastDStateTransitionStatusUnknown</b></li>
<li><b>LastDStateTransitionD3hot</b></li>
<li><b>LastDStateTransitionD3cold</b></li>
</ul>
 The <b>LastDStateTransitionD3cold</b> value indicates that the most recent transition to D3hot was followed by a transition to D3cold. For more information, see Remarks.

## -remarks

This routine tries to get the information needed to answer the caller's query from the parent bus driver and platform firmware. If this information is not available, the routine writes the value <b>LastDStateTransitionStatusUnknown</b> to the location pointed to by <i>the LastTransitionStatus</i> parameter.

For more information, see <a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_d3cold_last_transition_status">D3COLD_LAST_TRANSITION_STATUS</a>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/ne-wdm-_d3cold_last_transition_status">D3COLD_LAST_TRANSITION_STATUS</a>



<a href="/windows-hardware/drivers/ddi/wdm/ns-wdm-_d3cold_support_interface">D3COLD_SUPPORT_INTERFACE</a>

