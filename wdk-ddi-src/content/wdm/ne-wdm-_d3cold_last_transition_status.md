---
UID: NE:wdm._D3COLD_LAST_TRANSITION_STATUS
title: _D3COLD_LAST_TRANSITION_STATUS (wdm.h)
description: The D3COLD_LAST_TRANSITION_STATUS enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.
old-location: kernel\d3cold_last_transition_status.htm
tech.root: kernel
ms.date: 04/30/2018
keywords: ["D3COLD_LAST_TRANSITION_STATUS enumeration"]
ms.keywords: "*PD3COLD_LAST_TRANSITION_STATUS, D3COLD_LAST_TRANSITION_STATUS, D3COLD_LAST_TRANSITION_STATUS enumeration [Kernel-Mode Driver Architecture], LastDStateTransitionD3cold, LastDStateTransitionD3hot, LastDStateTransitionStatusUnknown, _D3COLD_LAST_TRANSITION_STATUS, kernel.d3cold_last_transition_status, wdm/D3COLD_LAST_TRANSITION_STATUS, wdm/LastDStateTransitionD3cold, wdm/LastDStateTransitionD3hot, wdm/LastDStateTransitionStatusUnknown"
req.header: wdm.h
req.include-header: Wdm.h
req.target-type: Windows
req.target-min-winverclnt: 
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
targetos: Windows
req.typenames: D3COLD_LAST_TRANSITION_STATUS, *PD3COLD_LAST_TRANSITION_STATUS
f1_keywords:
 - _D3COLD_LAST_TRANSITION_STATUS
 - wdm/_D3COLD_LAST_TRANSITION_STATUS
 - PD3COLD_LAST_TRANSITION_STATUS
 - wdm/PD3COLD_LAST_TRANSITION_STATUS
 - D3COLD_LAST_TRANSITION_STATUS
 - wdm/D3COLD_LAST_TRANSITION_STATUS
topic_type:
 - APIRef
 - kbSyntax
api_type:
 - HeaderDef
api_location:
 - Wdm.h
api_name:
 - D3COLD_LAST_TRANSITION_STATUS
---

# _D3COLD_LAST_TRANSITION_STATUS enumeration


## -description

The <b>D3COLD_LAST_TRANSITION_STATUS</b> enumeration indicates whether the most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.

## -enum-fields

### -field LastDStateTransitionStatusUnknown

Information is not available from the bus driver or platform firmware about whether the most recent transition to D3hot was followed by a transition to D3cold.

### -field LastDStateTransitionD3hot

The most recent transition to the D3hot device power state was not followed by a transition to the D3cold device power state.

### -field LastDStateTransitionD3cold

The most recent transition to the D3hot device power state was followed by a transition to the D3cold device power state.

## -remarks

The <i>LastTransitionStatus</i> parameter of the <a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-get_d3cold_last_transition_status">GetLastTransitionStatus</a> routine is a pointer to a variable of type <b>D3COLD_LAST_TRANSITION_STATUS</b>.

## -see-also

<a href="/windows-hardware/drivers/ddi/wdm/nc-wdm-get_d3cold_last_transition_status">GetLastTransitionStatus</a>
